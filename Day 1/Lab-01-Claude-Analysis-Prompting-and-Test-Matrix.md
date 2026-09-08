# Lab 01 - Claude Analysis, Prompt Engineering, and Test Matrix Design

## Lab Name
Code Understanding and Prompt Engineering for Enterprise .NET

## Description
This lab teaches participants how to use Claude to understand business logic and produce useful engineering analysis. It combines code explanation, review prompt design, and test matrix discovery.

## Prerequisites
- Completion of Lab 00
- Working OrderManagement solution
- Claude access
- Familiarity with C# and xUnit basics

## Technology Used
- C#
- .NET class libraries
- Claude prompt engineering
- xUnit (test planning stage)

## Business Use Case / Scenario
The Order Fulfillment Platform calculates totals and applies discount logic. Before modifying behavior, engineers must understand current behavior, identify ambiguities, and design tests.

## Folder Structure Context

```text
OrderManagement
|-- src
|   |-- OrderManagement.Application
|   |-- OrderManagement.Domain
|-- tests
|   |-- OrderManagement.Tests
```

## Setup Project Artifacts

### Step 1 - Create domain models

Create src/OrderManagement.Domain/Order.cs:

```csharp
namespace OrderManagement.Domain;

public class Order
{
    public Guid Id { get; set; }
    public Guid CustomerId { get; set; }
    public List<OrderItem> Items { get; set; } = new();
    public decimal Total { get; set; }
    public DateTime CreatedAtUtc { get; set; }
}
```

Create src/OrderManagement.Domain/OrderItem.cs:

```csharp
namespace OrderManagement.Domain;

public class OrderItem
{
    public Guid ProductId { get; set; }
    public int Quantity { get; set; }
    public decimal UnitPrice { get; set; }
}
```

### Step 2 - Create initial calculator

Create src/OrderManagement.Application/OrderCalculator.cs:

```csharp
using OrderManagement.Domain;

namespace OrderManagement.Application;

public class OrderCalculator
{
    public decimal Calculate(Order order)
    {
        decimal total = 0;

        foreach (var item in order.Items)
        {
            total += item.UnitPrice * item.Quantity;
        }

        if (total > 5000)
        {
            total *= 0.90m;
        }

        return total;
    }
}
```

### Step 3 - Compare weak vs structured explanation prompt

Weak prompt:

```text
Explain this code.
```

Structured prompt:

```text
Role:
Act as a senior .NET developer reviewing an unfamiliar
enterprise Order Management application.

Context:
The method calculates an order total before an order
is persisted.

Task:
Explain the current behaviour.

Constraints:
Do not modify the code.
Do not assume requirements that are not visible.

Expected Output:
1. Current logic
2. Business rules discovered
3. Assumptions
4. Edge cases
5. Potential maintainability concerns
```

### Step 4 - Introduce a realistic service for review

Create src/OrderManagement.Application/OrderService.cs:

```csharp
using OrderManagement.Domain;

namespace OrderManagement.Application;

public class OrderService
{
    public async Task<Order> CreateOrderAsync(Order order)
    {
        if (order == null)
            throw new Exception("Invalid order");

        decimal total = 0;

        foreach (var item in order.Items)
        {
            total += item.UnitPrice * item.Quantity;
        }

        if (total > 5000)
        {
            total *= 0.9m;
        }

        order.Total = total;
        order.Id = Guid.NewGuid();
        order.CreatedAtUtc = DateTime.UtcNow;

        await Task.Delay(10);

        return order;
    }
}
```

### Step 5 - Build a production review prompt

```text
Role:
Senior .NET code reviewer.

Context:
This service belongs to an ASP.NET Core enterprise
Order Management API.

Task:
Review CreateOrderAsync.

Constraints:
- Do not rewrite code yet.
- Do not introduce new dependencies.
- Preserve existing public contracts.
- Distinguish bugs from improvements.

Review Areas:
- correctness
- maintainability
- input validation
- async usage
- domain logic
- testability
- security

Expected Output:
Severity | Finding | Why It Matters | Recommendation
```

### Step 6 - Use few-shot format

```text
Example:

Code:
service.GetCustomer(id).Result

Finding:
Severity: High
Category: Async
Issue: Blocking asynchronous operation
Impact: Thread starvation under load
Recommendation: Use await with asynchronous API
```

Then ask:

```text
Review OrderService using the same reporting format.
```

### Step 7 - Create test matrix before test code

```text
Role:
Senior .NET test engineer.

Context:
OrderService creates orders.

Business Rule:
A 10% discount is applied when total exceeds 5000.

Task:
Create a test matrix.

Constraints:
Do not generate test code yet.

Include:
- happy paths
- boundaries
- invalid inputs
- null handling
- collection cases
- monetary edge cases

Expected Output:
Scenario | Input | Expected Result | Reason
```

Expected scenarios include:
- Order total < 5000
- Order total = 5000
- Order total > 5000
- Empty item list
- Null order
- Null items
- Quantity = 0
- Quantity < 0
- UnitPrice = 0
- UnitPrice < 0
- Multiple items
- Large monetary value

### Step 8 - Generate tests from approved matrix

```text
Generate xUnit tests from the approved test matrix.

Constraints:
- Use Arrange / Act / Assert.
- Avoid implementation-detail testing.
- Use descriptive test names.
```

Run tests:

```bash
dotnet test
```

## Expected Output
- Claude explanations are more precise with structured prompts
- Participants separate facts from assumptions
- Review findings are consistently formatted
- A complete test matrix is approved before generating test code
- xUnit tests execute successfully

## Conclusion
Prompt quality determines analysis quality. Senior engineers should force structure into AI interactions and validate outputs before implementation.