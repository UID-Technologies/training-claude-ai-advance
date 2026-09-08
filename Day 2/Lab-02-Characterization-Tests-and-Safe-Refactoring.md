# Lab 02 - Characterization Tests and Safe Refactoring

## Lab Name
Behavior Preservation Through Characterization Testing and Controlled Refactoring

## Description
This lab establishes a safety net by capturing existing behavior with tests before refactoring the legacy service.

## Prerequisites
- Completion of Labs 00-01
- LoanService baseline available
- xUnit project configured

## Technology Used
- xUnit
- Claude-assisted behavior matrix design
- C# refactoring patterns

## Business Use Case / Scenario
The team must improve maintainability without unintentionally changing current loan approval behavior used in production.

## Step-by-Step Details

### Step 1 - Generate characterization matrix

```text
Analyze ProcessLoan.

Do not refactor it.

Identify all externally observable behaviours.

Create a characterization-test matrix covering:
- approved loans
- rejected loans
- manual review
- invalid customer
- invalid amount
- credit-score boundaries
- amount boundaries
```

### Step 2 - Validate expected boundary scenarios

Examples:
- CreditScore 651, Amount 100000 -> Approved
- CreditScore 650 -> Rejected
- Amount 499999 -> Approved
- Amount 500000 -> ManualReview

### Step 3 - Generate xUnit characterization tests

```text
Generate xUnit characterization tests.

Constraints:
- Test observable behaviour only
- Do not test private implementation
- Preserve current behaviour
- Use descriptive test names
```

### Step 4 - Run tests

```bash
dotnet test
```

### Step 5 - Refactor plan only

```text
Review LoanService.

Goal:
Improve maintainability and testability.

Constraints:
- Preserve current public behaviour
- Do not change business rules
- Do not introduce a framework
- Do not change project structure unnecessarily
- Existing characterization tests must continue to pass

First propose the refactoring plan only.
```

### Step 6 - Implement limited improvements

Implement only selected changes:
- Introduce named constants
- Add custom validation exceptions
- Extract decision method
- Introduce clock abstraction

Example constants:

```csharp
public static class LoanRules
{
    public const int MinimumCreditScore = 650;
    public const decimal ManualReviewThreshold = 500000m;
}
```

Example decision extraction:

```csharp
private static string DetermineStatus(decimal amount, int creditScore)
{
    if (creditScore <= LoanRules.MinimumCreditScore)
        return "Rejected";

    if (amount >= LoanRules.ManualReviewThreshold)
        return "ManualReview";

    return "Approved";
}
```

### Step 7 - Re-run test suite

```bash
dotnet test
```

## Expected Output
- Characterization tests cover core and boundary behavior
- Refactoring improves readability/testability
- Existing behavior remains unchanged

## Conclusion
Safe modernization requires behavior capture first, then constrained refactoring validated by automated tests.