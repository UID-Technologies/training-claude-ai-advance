# Lab 03 - Regression Testing and AI-Assisted Debugging

## Lab Name
Defect Reproduction, Root-Cause Analysis, and Minimal Fix Workflow

## Description
This lab trains participants to use Claude for debugging with engineering discipline: reproduce defect, create failing test, apply minimal fix, and validate regression.

## Prerequisites
- Completion of Labs 00-02
- Existing OrderService implementation
- xUnit test project configured

## Technology Used
- C#
- xUnit
- Claude root-cause prompting
- .NET CLI testing

## Business Use Case / Scenario
Production defect: orders with negative quantity produce incorrect totals.

## Folder Structure Context

```text
OrderManagement
|-- src
|   |-- OrderManagement.Application
|   |-- OrderManagement.Domain
|-- tests
|   |-- OrderManagement.Tests
```

## Step-by-Step Details

### Step 1 - Reproduce defect with concrete data

Example order payload:

```csharp
var order = new Order
{
    Items =
    {
        new OrderItem
        {
            Quantity = -2,
            UnitPrice = 100
        }
    }
};
```

Observed output may be:

```text
-200
```

### Step 2 - Ask for diagnosis, not direct fix

```text
Observed Behaviour:
An order containing a negative quantity produces
a negative total.

Expected Behaviour:
Invalid order quantities should not be accepted.

Task:
Perform root-cause analysis.

Return:
1. direct cause
2. underlying design issue
3. affected layer
4. proposed validation location
5. regression tests required

Do not modify code.
```

### Step 3 - Generate smallest failing regression test

```text
Generate the smallest xUnit regression test
that reproduces this defect.

The test should fail against the current implementation.
```

Run tests:

```bash
dotnet test
```

Confirm regression test fails.

### Step 4 - Apply minimal maintainable fix

```text
Implement the smallest maintainable fix.

Do not refactor unrelated code.
```

### Step 5 - Validate again

```bash
dotnet test
```

Expected:
- Regression test passes
- Existing tests still pass

### Step 6 - Team retrospective

Capture this standard workflow:

```text
Bug
 -> Reproduce
 -> Failing Test
 -> Root Cause
 -> Minimal Fix
 -> Regression Validation
```

## Expected Output
- Defect is reproducible and documented
- Regression test fails before fix and passes after fix
- Fix scope remains minimal
- Existing behavior remains stable

## Conclusion
AI-assisted debugging must be test-first and evidence-driven. Root cause and regression validation are mandatory for safe delivery.