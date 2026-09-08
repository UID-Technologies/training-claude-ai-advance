# Lab 02 - Repository Understanding and AI-Assisted Feature Development

## Lab Name
Scoped Repository Analysis and Inventory Validation Feature Design

## Description
This lab teaches participants to use Claude Code for repository-level understanding, scoped analysis, and safe feature design before implementation.

## Prerequisites
- Completion of Lab 00 and Lab 01
- Existing OrderService in application layer
- Claude Code access in editor

## Technology Used
- Claude Code
- C# and ASP.NET Core architecture patterns
- Dependency injection design
- CancellationToken usage

## Business Use Case / Scenario
Orders must be rejected when requested product quantities are unavailable in inventory maintained by an external service.

## Folder Structure Context

```text
OrderManagement
|-- src
|   |-- OrderManagement.Api
|   |-- OrderManagement.Application
|   |-- OrderManagement.Domain
|   |-- OrderManagement.Infrastructure
|-- tests
|   |-- OrderManagement.Tests
```

## Setup Project (Analysis First)

### Step 1 - Open repository root

```bash
cd claude-dotnet-day1
```

### Step 2 - Ask for repository discovery

```text
Analyze this repository.

Do not make any modifications.

Explain:
1. Solution structure
2. Purpose of each project
3. Project dependencies
4. Domain entities
5. Existing order-processing logic
6. Current tests
7. Architecture concerns

Reference actual files where possible.
```

### Step 3 - Scope to relevant files only

```text
We need to change order creation.

Identify only the projects and files relevant
to order creation.

Do not analyze unrelated components.
```

### Step 4 - Trace execution flow

```text
Trace the order creation flow from the public
application entry point to the calculation logic.

Identify important methods and dependencies.

Do not modify code.
```

## Feature Development Workflow

### Step 5 - Define requirement clearly

Requirement:

```text
Before accepting an order, confirm that every
requested product has sufficient inventory.

If one product does not have enough stock,
the order must be rejected.
```

### Step 6 - Ask Claude for design, not code

```text
Role:
Senior .NET solution developer.

Context:
This is the existing Order Management solution.

Requirement:
Validate inventory before accepting an order.

Constraints:
- Inventory belongs to an external service.
- Application layer must not directly create HttpClient.
- Keep solution testable.
- Do not move business logic into controllers.
- Minimize changes.
- Do not add third-party libraries.

Task:
Propose the implementation design.

Expected Output:
1. Files affected
2. New abstractions
3. Execution flow
4. Error handling
5. Testing strategy
6. Risks

Do not write code yet.
```

### Step 7 - Add abstraction

Define inventory service contract concept:

```csharp
public interface IInventoryService
{
    Task<bool> IsAvailableAsync(
        Guid productId,
        int quantity,
        CancellationToken cancellationToken);
}
```

### Step 8 - Integrate in OrderService

Conceptual flow:

```csharp
foreach (var item in order.Items)
{
    var available =
        await _inventoryService.IsAvailableAsync(
            item.ProductId,
            item.Quantity,
            cancellationToken);

    if (!available)
    {
        throw new InsufficientInventoryException(item.ProductId);
    }
}
```

### Step 9 - Add cancellation support

Ensure public async flow accepts and passes CancellationToken to all external calls.

### Step 10 - Run AI self-review on changed scope

```text
Review only the inventory-related changes as if
this were a production pull request.

Check:
- correctness
- async implementation
- cancellation
- dependency injection
- error handling
- performance
- backwards compatibility
- unnecessary changes

Do not modify code.

Return findings first.
```

### Step 11 - Performance discussion

Discuss whether API supports:
- Batch inventory check endpoint
- Controlled parallel calls

Do not optimize blindly. Confirm external API behavior first.

## Expected Output
- Participants can scope analysis to relevant files
- Inventory validation design introduced through abstraction
- Cancellation flows are explicit
- AI-generated design is reviewed critically

## Conclusion
AI is most effective when used with disciplined context scoping, contract-first design, and explicit review before coding.