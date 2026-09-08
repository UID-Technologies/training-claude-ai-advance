# Day 2 Hands-on Lab Manual

## .NET Modernization, Quality, Security, and Automated Testing with Claude

This Day 2 content is reorganized into structured lab modules for easier delivery, clearer sequencing, and better hands-on execution.

## Audience
Experienced .NET developers, senior developers, technical leads, and solution architects.

## Difficulty
Intermediate

## Day 2 Business Scenario
Legacy Loan Processing Platform modernization with minimal risk.

## Day 2 Objectives
Participants use Claude to:
- Analyze legacy systems
- Prioritize technical debt
- Plan incremental modernization
- Preserve behavior with tests
- Perform secure and test-driven changes

## Lab Modules

1. Lab 00: Legacy solution setup
   - File: Lab-00-Legacy-Solution-Setup.md

2. Lab 01: Legacy analysis and modernization planning
   - File: Lab-01-Legacy-Analysis-and-Modernization-Planning.md

3. Lab 02: Characterization tests and safe refactoring
   - File: Lab-02-Characterization-Tests-and-Safe-Refactoring.md

4. Lab 03: Code quality, bug analysis, and regression workflow
   - File: Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md

5. Lab 04: Security review and remediation
   - File: Lab-04-Security-Review-and-Remediation.md

6. Lab 05: xUnit, NUnit, and mocking dependencies
   - File: Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md

7. Lab 06: Failing test diagnosis, test gap review, and capstone
   - File: Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md

8. Trainer evaluation checklist
   - File: Trainer-Evaluation-Checklist.md

## Shared Prerequisites
- .NET SDK
- Visual Studio, VS Code, or Rider
- Git
- Claude access
- Claude Code where available
- xUnit and NUnit familiarity
- Moq or equivalent mocking library
- Terminal or PowerShell

## Verify Environment

```bash
dotnet --version
git --version
```

## Recommended Sequence
Lab 00 -> Lab 01 -> Lab 02 -> Lab 03 -> Lab 04 -> Lab 05 -> Lab 06

## Delivery Notes for Trainers
- Require analysis before refactoring.
- Require characterization tests before risky changes.
- Require failing regression tests before bug fixes.
- Require security review before and after remediation.
- Require final validation and PR-quality summary.
