# Lab 05 - Tool Use and Agentic Workflow

## Lab Name
Inventory Tool Calling and Multi-Step Agent Reasoning

## Description
This lab demonstrates how AI should call tools for live enterprise data instead of guessing, and how to orchestrate multi-step reasoning across order, customer, and inventory checks.

## Prerequisites
- Completion of Labs 00-04
- OrderManagement API running
- Basic understanding of tool/function calling concepts

## Technology Used
- ASP.NET Core minimal APIs
- Tool schema design
- Agentic reasoning pattern

## Business Use Case / Scenario
Business asks whether specific orders can be fulfilled. AI must verify data from live inventory and related systems.

## Folder Structure Context

```text
OrderManagement
|-- src
|   |-- OrderManagement.Api
```

## Step-by-Step Details

### Step 1 - Add demo inventory endpoint

In API project, add:

```csharp
app.MapGet(
    "/api/inventory/{productId}",
    (string productId) =>
    {
        var stock =
            new Dictionary<string, int>
            {
                ["P1001"] = 10,
                ["P1002"] = 0,
                ["P1003"] = 25
            };

        if (!stock.TryGetValue(productId, out var quantity))
        {
            return Results.NotFound();
        }

        return Results.Ok(new
        {
            productId,
            available = quantity
        });
    });
```

### Step 2 - Define tool contract

Tool name:

```text
get_inventory
```

Description:

```text
Returns current available inventory for a product.
Use this tool whenever current stock is required.
```

Input schema:

```json
{
  "productId": "string"
}
```

### Step 3 - Run success scenario

Business question:

```text
Can we fulfill an order containing:

P1001 quantity 5
P1003 quantity 4?
```

Expected reasoning:

```text
Need inventory -> get_inventory(P1001) -> 10
Need inventory -> get_inventory(P1003) -> 25
Both sufficient -> order can proceed
```

### Step 4 - Run failure scenario

Business question:

```text
Can we fulfill:

P1001 quantity 5
P1002 quantity 2?
```

Expected conclusion:

```text
Order cannot be fulfilled.
P1002 shortage = 2.
```

### Step 5 - Expand to agentic multi-tool flow

Define conceptual tools:
- get_order(orderId)
- get_customer(customerId)
- get_inventory(productId)

Sample order data:

```text
ORD-1001
Customer: CUST-001
Items: P1001 x 5, P1002 x 2
```

Reasoning pattern:

```text
Goal -> Reason -> Tool -> Result -> Next Action
```

### Step 6 - Discuss guardrails

Classify tools by risk:
- Read: get_order (low risk)
- Write: update_order (higher risk)
- Destructive: cancel_order, delete_customer, issue_refund (strict controls required)

## Expected Output
- AI calls tools for live data instead of assuming answers
- Multi-step order decision reasoning is transparent
- Teams understand action risk and guardrails

## Conclusion
Agentic workflows are reliable when tools are explicit, reasoning is auditable, and destructive operations are strongly controlled.