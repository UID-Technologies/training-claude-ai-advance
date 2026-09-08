# Lab 06 - Failing Test Diagnosis, Test Gap Review, and Capstone

## Lab Name
Failure Analysis, Coverage Confidence, and Policy-Driven Change Delivery

## Description
This lab closes Day 2 with advanced test diagnostics, gap analysis, and a testing-first capstone implementation.

## Prerequisites
- Completion of Labs 00-05
- Existing LoanService tests
- Ability to run full test suite

## Technology Used
- Claude-assisted failure diagnosis
- Regression principles
- Test gap prioritization
- Capstone-level requirement analysis

## Business Use Case / Scenario
A new policy must be introduced while preserving existing behavior. Teams must diagnose failures correctly, add missing tests, and deliver the change safely.

## Step-by-Step Details

### Part A - Analyze failing tests

Step 1 - Introduce incorrect test assertion

Example mismatch:

```csharp
Assert.Equal("Approved", result.Status);
```

for a scenario such as CreditScore 600.

Step 2 - Run suite:

```bash
dotnet test
```

Step 3 - Ask Claude to diagnose source of failure:

```text
Analyze this failing unit test.

Do not change code yet.

Determine whether the failure is caused by:
1. production-code defect
2. incorrect test expectation
3. ambiguous requirement
4. incorrect mock setup

Explain your reasoning.
```

### Part B - Regression test permanence

Step 1 - Ensure defect test reproduces issue before fix.

Step 2 - Apply fix.

Step 3 - Confirm defect test passes.

Step 4 - Keep the test in suite permanently.

Principle:

```text
Every meaningful bug should increase
permanent knowledge in the test suite.
```

### Part C - AI-assisted test review

Ask Claude:

```text
Review the current LoanService production code
and its unit tests.

Do not generate code.

Identify:
1. business branches not tested
2. missing boundaries
3. missing negative scenarios
4. missing dependency failures
5. overly implementation-coupled tests
6. redundant tests

Return a prioritized list.
```

Select only high-value gaps. Do not optimize for coverage percentage alone.

### Part D - Testing-focused capstone

New policy:

```text
Loans above 750,000 require both
credit score of at least 700 and manual approval.
```

Existing behavior must remain for smaller loans.

Step 1 - Requirement analysis:
- Impacted rules
- Conflicts with existing 500,000 threshold
- Boundary ambiguities
- Impacted methods
- Required test scenarios

Step 2 - Clarify boundaries:
- Exactly 750,000 behavior
- Whether 700 is inclusive
- Rule ordering
- Final status behavior
- Existing loan impact

Step 3 - Build test matrix with combinations:
- Amount < 500000
- Amount = 500000
- Amount between 500000 and 750000
- Amount = 750000
- Amount > 750000
- CreditScore < 700
- CreditScore = 700
- CreditScore > 700

Step 4 - Add tests before code changes.

Step 5 - Implement smallest maintainable change:

```text
Implement the smallest maintainable change
that satisfies the approved test matrix.

Do not redesign unrelated code.
```

Step 6 - Run full suite:

```bash
dotnet test
```

Step 7 - Run security review on changed code.

Step 8 - Run AI code review for correctness, maintainability, testability, complexity, and regression risk.

Step 9 - Generate PR summary with:
- Title
- Requirement
- Implementation summary
- Test coverage
- Security considerations
- Known risks
- Reviewer checklist

## Expected Output
- Teams diagnose failing tests before changing code
- Regression tests are permanent artifacts
- High-value test gaps are closed
- Capstone change is delivered test-first with review and validation

## Conclusion
Production-safe modernization requires reasoning discipline, not just code generation. Testing and validation are the control system for AI-assisted delivery.