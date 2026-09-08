# Lab 03 - Code Quality, Bug Analysis, and Regression Workflow

## Lab Name
Structured Quality Review, Root-Cause Analysis, and Minimal Defect Remediation

## Description
This lab combines AI-assisted quality review with disciplined defect handling: diagnose, test first, minimal fix, and regression validation.

## Prerequisites
- Completion of Labs 00-02
- Existing LoanService and tests

## Technology Used
- Claude structured code review prompts
- xUnit regression testing
- .NET CLI test workflow

## Business Use Case / Scenario
Production reports that loans with amount 0 are being approved. The team must diagnose accurately and fix safely.

## Step-by-Step Details

### Step 1 - Run quality review

```text
Act as a production .NET code reviewer.

Review LoanService for:
- readability
- complexity
- duplication
- naming
- responsibilities
- coupling
- testability

Do not discuss security yet.

Return:
Severity
Finding
Evidence
Impact
Recommended improvement
```

### Step 2 - Confirm issue prioritization

Discuss that not every code smell requires immediate action. Prioritize by risk, business impact, and change frequency.

### Step 3 - Reproduce defect

Current validation allows amount 0 because condition is:

```csharp
if (amount < 0)
```

### Step 4 - Ask for root-cause analysis

```text
Observed Behaviour:
A loan with amount = 0 is processed.

Expected Behaviour:
Loan amount must be greater than zero.

Task:
Perform root-cause analysis.

Do not modify code.

Return:
1. Direct cause
2. Why current validation permits it
3. Correct validation rule
4. Regression test
5. Minimal fix
6. Possible side effects
```

### Step 5 - Create failing regression test

Example skeleton:

```csharp
[Fact]
public void ProcessLoan_ShouldReject_ZeroAmount()
{
    // Arrange

    // Act

    // Assert
}
```

Run and confirm failure:

```bash
dotnet test
```

### Step 6 - Apply minimal fix

Expected update:

```csharp
if (amount <= 0)
```

### Step 7 - Validate regression closure

```bash
dotnet test
```

Regression test must pass and previous tests remain green.

## Expected Output
- Quality findings are actionable and prioritized
- Defect is reproducible
- Regression test fails before fix and passes after fix
- Minimal code change resolves issue safely

## Conclusion
The reliable bug workflow is diagnose first, test first, fix minimally, and validate fully.