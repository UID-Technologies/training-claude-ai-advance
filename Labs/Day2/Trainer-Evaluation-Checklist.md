# Day 2 Trainer Evaluation Checklist

## Purpose
Evaluate participant readiness for safe modernization of legacy .NET systems using AI-assisted workflows.

## Evaluation Criteria

### Modernization Judgment
- Avoids unnecessary rewrites
- Chooses incremental change strategy

### Technical Debt Prioritization
- Distinguishes defects from maintainability concerns
- Prioritizes by business and technical risk

### Behavior Preservation
- Creates characterization tests before refactoring
- Protects existing business behavior

### Root-Cause Discipline
- Diagnoses before fixing
- Uses evidence from tests and code paths

### Security Practice
- Detects practical vulnerabilities
- Applies minimal secure remediation
- Re-validates after changes

### Test Design Quality
- Uses matrix-first approach
- Covers boundaries and negative scenarios
- Uses appropriate Fact, Theory, and parameterized styles

### Mocking Strategy
- Isolates real dependencies
- Verifies only meaningful interactions
- Covers dependency failure scenarios

### Regression Maturity
- Converts defects into permanent tests
- Confirms fail-before and pass-after behavior

### AI Usage Quality
- Uses Claude for analysis, review, and validation
- Does not rely on blind code generation

## Day 2 Deliverables Checklist
- Legacy .NET solution
- Technical debt assessment
- Modernization plan
- Characterization test suite
- Refactored LoanService
- Bug regression test
- Security review report
- Security remediation
- xUnit suite
- NUnit comparison tests
- Mock-based service tests
- Dependency-failure tests
- Test-gap analysis
- Testing-focused capstone
- PR summary

## Final Learning Outcome
Claude accelerates modernization work, but production safety comes from disciplined engineering: analysis, scoped change, testing, security checks, and human approval.