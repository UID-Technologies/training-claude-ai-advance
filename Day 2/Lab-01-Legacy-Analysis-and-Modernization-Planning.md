# Lab 01 - Legacy Analysis and Modernization Planning

## Lab Name
Repository Analysis, Technical Debt Classification, and Phased Modernization Plan

## Description
This lab trains participants to analyze legacy code safely and create an incremental modernization roadmap rather than rewriting the system.

## Prerequisites
- Completion of Lab 00
- Claude Code access
- Working LegacyLoanProcessing solution

## Technology Used
- Claude Code repository analysis
- Prompt engineering for architecture and debt assessment
- Incremental modernization planning

## Business Use Case / Scenario
The legacy loan-processing system is business-critical and cannot be rewritten all at once. Teams must identify and prioritize improvements by risk and impact.

## Step-by-Step Details

### Step 1 - Repository analysis prompt

```text
Act as a senior .NET modernization architect.

Analyze this repository.

Do not modify files.

Identify:
1. Solution structure
2. Project dependencies
3. Architectural style
4. Business responsibilities
5. Technical debt
6. Security concerns
7. Testability issues
8. Performance concerns
9. Areas that should not be changed without clarification
```

### Step 2 - Review and validate findings

Typical findings to confirm:
- Generic exceptions
- Random ID generation
- DateTime.Now usage
- Magic numbers
- Mixed responsibilities
- Console logging
- Lack of interfaces
- Weak validation
- Hard-coded status strings
- Missing tests

### Step 3 - Classify findings

Use three categories:
- Actual defect
- Design or maintainability issue
- Future modernization opportunity

### Step 4 - Generate phased modernization plan

```text
Role:
Senior .NET modernization architect.

Context:
This is a business-critical legacy loan-processing service.

Constraint:
We cannot rewrite the system.
Modernization must be incremental.

Task:
Create a modernization plan.

Expected Output:
For each recommendation provide:
- Problem
- Risk
- Business impact
- Technical impact
- Priority
- Recommended change
- Validation required

Organize recommendations into:
Phase 1 - Low-risk improvements
Phase 2 - Structural improvements
Phase 3 - Larger modernization opportunities
```

### Step 5 - Prioritize and finalize roadmap

Expected direction:
- Phase 1: tests, validation, exceptions, constants, logging
- Phase 2: interfaces, decision extraction, dependency injection
- Phase 3: async modernization, persistence improvements, API redesign, observability

## Expected Output
- Clear debt inventory with category-based classification
- Practical phased roadmap approved by team
- Explicit modernization boundaries to reduce risk

## Conclusion
Modernization succeeds when analysis is evidence-based and improvements are prioritized incrementally by business risk and delivery value.