# Claude AI for .NET Developers

## 2-Day Hands-on Advance Training

This repository is the participant and trainer guide for a **two-day intermediate program** on using Claude across the .NET software development lifecycle.

The program is for experienced .NET developers, technical leads, and solution architects who want Claude as an engineering assistant — not only as a chatbot or a code generator.

| Day | Theme | Business scenario | Reference deck |
|---|---|---|---|
| **Day 1** | Claude AI and AI-assisted development | Enterprise Order Fulfillment Platform | [01 - Claude AI and AI-Assisted Development](References/01%20-%20Claude-AI-and-AI-Assisted-Development.pdf) |
| **Day 2** | Modernization, quality, security, and automated testing | Legacy Loan Processing Platform | [02 - .NET Modernization, Quality, Security, and Automated Testing](References/02%20-%20.NET-Modernization-Quality-Security-and-Automated-Testing.pdf) |

---

## Contents

- [Two-day training table of contents](#two-day-training-table-of-contents)
- [Program overview](#program-overview)
- [Who this program is for](#who-this-program-is-for)
- [Recommended experience](#recommended-experience)
- [Technology stack](#technology-stack)
- [Learning objectives](#learning-objectives)
- [Day 1 — Claude AI and AI-assisted development](#day-1--claude-ai-and-ai-assisted-development)
- [Day 2 — Modernization, quality, security, and testing](#day-2--modernization-quality-security-and-testing)
- [Labs](#labs)
- [References](#references)
- [Trainer resources](#trainer-resources)
- [Repository structure](#repository-structure)
- [How to use this repository](#how-to-use-this-repository)
- [Engineering principles](#engineering-principles)
- [Expected deliverables](#expected-deliverables)

---

## Two-Day Training Table of Contents

This is the program agenda. Use it as the primary map for lectures, labs, and reference material.

```text
DAY 1                              DAY 2
Claude AI & AI-Assisted            .NET Modernization, Quality,
Development                        Security & Automated Testing
        |                                      |
Prompt Engineering                 Legacy Analysis
        |                                      |
Repository Understanding           Characterization Tests
        |                                      |
Feature Development                Safe Refactoring
        |                                      |
Debugging & Regression             Code Quality & Defects
        |                                      |
Claude API Integration             Security Review
        |                                      |
Tool Use & MCP                     xUnit, NUnit & Mocking
        |                                      |
Day 1 Challenge                    Testing Capstone
```

### Day 1 — Claude AI and AI-Assisted Development

**Reference:** [01 - Claude AI and AI-Assisted Development](References/01%20-%20Claude-AI-and-AI-Assisted-Development.pdf)

| Session | Topic | Focus | Lab |
|---|---|---|---|
| Setup | Base solution | Create the Order Management solution used for the rest of Day 1 | [Lab 00 — Base Solution Setup](Labs/Day1/Lab-00-Base-Solution-Setup.md) |
| Module 1 | Claude platform and models | Model selection, context windows, tokens, cost, Claude Code, validation | Lecture — see [Day 1 deck](References/01%20-%20Claude-AI-and-AI-Assisted-Development.pdf) |
| Module 2 | Prompt engineering for developers | Role → Context → Task → Constraints → Expected Output; test matrices | [Lab 01 — Analysis, Prompting, and Test Matrix](Labs/Day1/Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md) |
| Module 3 | Claude Code and developer productivity | Repository understanding, scoped change, feature design, tests, PR summary | [Lab 02 — Repository Understanding and Feature Development](Labs/Day1/Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md) |
| Practice | Debugging and regression | Reproduce defect, failing test, minimal fix, keep the regression test | [Lab 03 — Regression Testing and AI-Assisted Debugging](Labs/Day1/Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md) |
| Practice | Claude-enabled API | Secure API-key handling and a structured code-review endpoint | [Lab 04 — Claude-Enabled API Code Review Service](Labs/Day1/Lab-04-Claude-Enabled-API-Code-Review-Service.md) |
| Module 4 | Tool use and agentic workflow | Function calling, live data, multi-step reason → tool → result | [Lab 05 — Tool Use and Agentic Workflow](Labs/Day1/Lab-05-Tool-Use-and-Agentic-Workflow.md) |
| Close | MCP concepts and Day 1 challenge | RAG vs MCP; end-to-end AI-assisted delivery | [Lab 06 — MCP Concepts and Final Challenge](Labs/Day1/Lab-06-MCP-Concepts-and-Final-Challenge.md) |

**Suggested flow:** first half — platform, prompting, analysis. Second half — Claude Code, API integration, tools, MCP, challenge.

### Day 2 — .NET Modernization, Quality, Security, and Automated Testing

**Reference:** [02 - .NET Modernization, Quality, Security, and Automated Testing](References/02%20-%20.NET-Modernization-Quality-Security-and-Automated-Testing.pdf)

| Session | Topic | Focus | Lab |
|---|---|---|---|
| Setup | Legacy baseline | Create the imperfect Loan Processing solution used for Day 2 | [Lab 00 — Legacy Solution Setup](Labs/Day2/Lab-00-Legacy-Solution-Setup.md) |
| Module 5 | Legacy analysis and modernization | Technical debt, risk vs impact, incremental plan — not a rewrite | [Lab 01 — Legacy Analysis and Modernization Planning](Labs/Day2/Lab-01-Legacy-Analysis-and-Modernization-Planning.md) |
| Module 5 | Characterization and refactoring | Capture current behaviour, then refactor behind tests | [Lab 02 — Characterization Tests and Safe Refactoring](Labs/Day2/Lab-02-Characterization-Tests-and-Safe-Refactoring.md) |
| Module 6 | Code quality and defects | Code smells, root-cause analysis, minimal fix, regression test | [Lab 03 — Code Quality, Bug Analysis, and Regression](Labs/Day2/Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md) |
| Module 6 | Secure coding | Secrets, injection, authn vs authz, minimal secure remediation | [Lab 04 — Security Review and Remediation](Labs/Day2/Lab-04-Security-Review-and-Remediation.md) |
| Module 7 | xUnit, NUnit, and mocking | Test matrix first, parameterized tests, Moq, dependency failures | [Lab 05 — xUnit, NUnit, and Mocking Dependencies](Labs/Day2/Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md) |
| Close | Diagnosis and capstone | Failing-test diagnosis, coverage gaps, policy change delivered test-first | [Lab 06 — Failing Test Diagnosis, Test Gaps, and Capstone](Labs/Day2/Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md) |

**Suggested flow:** first half — modernization, quality, security. Second half — automated testing and capstone.

---

## Program Overview

Day 1 teaches Claude as an engineering assistant across the development lifecycle.

```text
Requirement → Understand → Design → Code → Review → Test → Debug → Document → Human Approval
```

Day 2 teaches Claude for modernization and quality on a legacy .NET application.

```text
Legacy Application → Analyze → Identify Debt → Plan → Refactor → Secure → Test → Validate
```

The program does not replace the software development lifecycle with AI. It inserts AI into a controlled workflow:

```text
Understand → Plan → Generate → Review → Secure → Test → Validate → Human Decision
```

---

## Who This Program Is For

- .NET developers and senior .NET developers
- Full-stack developers working with .NET
- Technical leads and solution architects
- Engineering leads
- Application modernization teams
- Developers evaluating AI-assisted engineering practices

## Recommended Experience

Participants should already be comfortable with:

- C# and .NET / ASP.NET Core
- Object-oriented programming
- REST APIs, dependency injection, and async programming
- Git and basic software architecture
- Basic unit-testing concepts

This is not an introductory C# or .NET course.

## Technology Stack

- .NET, ASP.NET Core, C#, Entity Framework Core, REST APIs, Git
- Claude, Claude Code, Anthropic API concepts
- Tool use / function calling, MCP, RAG
- xUnit, NUnit, Moq
- Postman or `.http` files
- Visual Studio, Visual Studio Code, or Rider

## Learning Objectives

By the end of the two days, participants should be able to:

- Select Claude models using complexity, context size, latency, and cost
- Apply context-management strategies on large repositories
- Write structured engineering prompts and review AI output before acceptance
- Use Claude Code to understand, change, and document an existing repository
- Use tool calling, MCP, and RAG in the right situations
- Analyze legacy .NET code, prioritize technical debt, and modernize incrementally
- Diagnose defects with evidence, apply a minimal fix, and keep a regression test
- Perform AI-assisted security reviews and remediate common vulnerabilities
- Design test matrices and write unit tests with xUnit, NUnit, and mocks

---

## Day 1 — Claude AI and AI-Assisted Development

**Objective:** use Claude through a controlled engineering workflow, not as a one-shot code generator.

**Scenario:** an enterprise-style **Order Fulfillment Platform**.

```text
Customer → Order → Order Items → Inventory → Payment / Processing
```

Order creation covers customer and item validation, inventory checks, totals, discounts, persistence, and order-number generation.

### Module 1 — Claude platform and models

- Claude model family, Console, API keys, context windows, and tokens
- Model selection by task, cost, and reasoning depth
- Progressive discovery for large repositories: structure → feature → files → dependencies → task
- Treat AI output as a proposal until it is reviewed, built, tested, and approved

### Module 2 — Prompt engineering for developers

Consistent prompt pattern used throughout the training:

```text
Role → Context → Task → Constraints → Expected Output
```

Include framework, runtime, architecture, business rules, and constraints. For tests, analyze the code and produce a test matrix before generating test code.

**Lab:** [Lab 01](Labs/Day1/Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md)

### Module 3 — Claude Code and developer productivity

- Understand the repository before changing it
- Locate relevant code, assess impact, design, then implement
- Reusable repository instructions for architecture, coding, testing, and security
- Feature work, documentation, and pull-request assistance

**Labs:** [Lab 00](Labs/Day1/Lab-00-Base-Solution-Setup.md) · [Lab 02](Labs/Day1/Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md) · [Lab 03](Labs/Day1/Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md) · [Lab 04](Labs/Day1/Lab-04-Claude-Enabled-API-Code-Review-Service.md)

### Module 4 — Tool use, MCP, and agentic development

Traditional interaction is prompt → response. Agentic interaction is:

```text
Goal → Reason → Select Tool → Execute → Observe → Reason Again → Next Action
```

- **RAG** answers: what information should Claude know?
- **MCP / tools** answer: what systems should Claude interact with?

**Labs:** [Lab 05](Labs/Day1/Lab-05-Tool-Use-and-Agentic-Workflow.md) · [Lab 06](Labs/Day1/Lab-06-MCP-Concepts-and-Final-Challenge.md)

Day 1 challenge: orders over 25,000 require a manual approval flag. Participants must clarify ambiguous boundaries and follow understand → design → test plan → implement → review → validate.

---

## Day 2 — Modernization, Quality, Security, and Testing

**Objective:** improve an existing .NET application without rewriting it.

**Scenario:** a **Legacy Loan Processing Platform**.

```text
Customer → Loan Application → Eligibility Rules → Credit Score → Loan Decision → Notification
```

Typical legacy problems: generic exceptions, hard-coded thresholds, string statuses, console logging, tight coupling, weak validation, security issues, and limited tests.

### Module 5 — Legacy .NET modernization

- Legacy is about change risk and maintainability, not only code age
- Classify debt by impact and risk; modernize incrementally
- Characterization tests capture current behaviour before refactoring

**Labs:** [Lab 00](Labs/Day2/Lab-00-Legacy-Solution-Setup.md) · [Lab 01](Labs/Day2/Lab-01-Legacy-Analysis-and-Modernization-Planning.md) · [Lab 02](Labs/Day2/Lab-02-Characterization-Tests-and-Safe-Refactoring.md)

### Module 6 — Code quality, defects, and secure coding

Defect workflow:

```text
Observed Problem → Evidence → Reproduce → Root Cause → Minimal Fix → Regression Test → Validate
```

Security review covers trust boundaries, input, authentication, authorization, data access, secrets, logging, and errors. Do not hard-code credentials; use user secrets or a secret store.

**Labs:** [Lab 03](Labs/Day2/Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md) · [Lab 04](Labs/Day2/Lab-04-Security-Review-and-Remediation.md)

### Module 7 — Automated testing with xUnit and NUnit

- Test matrix first: happy path, null/invalid input, boundaries, exceptions, dependency failures
- xUnit: `[Fact]`, `[Theory]`, `[InlineData]`
- NUnit: `[Test]`, `[TestCase]`, `[SetUp]`, `[TearDown]`
- Mock repositories and external services; avoid mocking implementation details
- Diagnose failing tests before changing production code

**Labs:** [Lab 05](Labs/Day2/Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md) · [Lab 06](Labs/Day2/Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md)

Day 2 capstone policy: loans above ₹750,000 require a credit score of at least 700 and manual approval. Deliver the change test-first, then review, secure, and validate.

---

## Labs

Hands-on exercises live under `Labs/`. Complete them in order. Setup labs (Lab 00) create the solutions used for the rest of that day.

### Day 1 labs — Order Fulfillment Platform

| Lab | Name | What you will do | File |
|---|---|---|---|
| 00 | Base solution setup | Create the multi-project Order Management solution | [Lab-00-Base-Solution-Setup.md](Labs/Day1/Lab-00-Base-Solution-Setup.md) |
| 01 | Analysis, prompting, and test matrix | Explain business logic, write structured prompts, design tests | [Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md](Labs/Day1/Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md) |
| 02 | Repository understanding and feature development | Scope Claude Code, design inventory validation, implement safely | [Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md](Labs/Day1/Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md) |
| 03 | Regression testing and debugging | Reproduce a defect, add a failing test, apply a minimal fix | [Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md](Labs/Day1/Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md) |
| 04 | Claude-enabled API code review | Integrate the Anthropic API securely and return structured findings | [Lab-04-Claude-Enabled-API-Code-Review-Service.md](Labs/Day1/Lab-04-Claude-Enabled-API-Code-Review-Service.md) |
| 05 | Tool use and agentic workflow | Call live inventory tools and reason across multiple steps | [Lab-05-Tool-Use-and-Agentic-Workflow.md](Labs/Day1/Lab-05-Tool-Use-and-Agentic-Workflow.md) |
| 06 | MCP concepts and final challenge | Classify RAG vs MCP, then deliver the Day 1 feature challenge | [Lab-06-MCP-Concepts-and-Final-Challenge.md](Labs/Day1/Lab-06-MCP-Concepts-and-Final-Challenge.md) |

### Day 2 labs — Legacy Loan Processing Platform

| Lab | Name | What you will do | File |
|---|---|---|---|
| 00 | Legacy solution setup | Create the deliberately imperfect loan-processing baseline | [Lab-00-Legacy-Solution-Setup.md](Labs/Day2/Lab-00-Legacy-Solution-Setup.md) |
| 01 | Legacy analysis and modernization planning | Assess debt and produce a phased modernization plan | [Lab-01-Legacy-Analysis-and-Modernization-Planning.md](Labs/Day2/Lab-01-Legacy-Analysis-and-Modernization-Planning.md) |
| 02 | Characterization tests and safe refactoring | Lock current behaviour, then refactor behind tests | [Lab-02-Characterization-Tests-and-Safe-Refactoring.md](Labs/Day2/Lab-02-Characterization-Tests-and-Safe-Refactoring.md) |
| 03 | Code quality, bugs, and regression | Review quality, diagnose a production defect, add a regression test | [Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md](Labs/Day2/Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md) |
| 04 | Security review and remediation | Find and fix secrets and injection issues, then re-validate | [Lab-04-Security-Review-and-Remediation.md](Labs/Day2/Lab-04-Security-Review-and-Remediation.md) |
| 05 | xUnit, NUnit, and mocking | Expand the suite, compare frameworks, isolate dependencies with Moq | [Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md](Labs/Day2/Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md) |
| 06 | Diagnosis, test gaps, and capstone | Diagnose failures, close high-value gaps, deliver the new loan policy | [Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md](Labs/Day2/Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md) |

---

## References

Slide decks and supporting material for each training day:

| Day | Document | Use |
|---|---|---|
| Day 1 | [01 - Claude-AI-and-AI-Assisted-Development.pdf](References/01%20-%20Claude-AI-and-AI-Assisted-Development.pdf) | Platform, prompting, Claude Code, tools, MCP, and agentic workflows |
| Day 2 | [02 - .NET-Modernization-Quality-Security-and-Automated-Testing.pdf](References/02%20-%20.NET-Modernization-Quality-Security-and-Automated-Testing.pdf) | Legacy analysis, quality, security, xUnit/NUnit, and the testing capstone |

Follow the matching day's deck while working through that day's labs.

---

## Trainer Resources

| Day | Checklist | Use |
|---|---|---|
| Day 1 | [Trainer Evaluation Checklist](Labs/Day1/Trainer-Evaluation-Checklist.md) | Prompt quality, engineering discipline, validation, architecture, and AI judgment |
| Day 2 | [Trainer Evaluation Checklist](Labs/Day2/Trainer-Evaluation-Checklist.md) | Modernization judgment, behaviour preservation, security, testing, and regression |

Suggested classroom pattern:

```text
Instructor Demo → Participant Exercise → Claude-Assisted Analysis → Implementation → Peer / AI Review → Validation → Trainer Discussion
```

Participants may work individually, in pairs, or in small teams.

---

## Repository Structure

```text
training-claude-ai-advance/
|-- README.md
|-- Labs/
|   |-- Day1/
|   |   |-- Lab-00-Base-Solution-Setup.md
|   |   |-- Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md
|   |   |-- Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md
|   |   |-- Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md
|   |   |-- Lab-04-Claude-Enabled-API-Code-Review-Service.md
|   |   |-- Lab-05-Tool-Use-and-Agentic-Workflow.md
|   |   |-- Lab-06-MCP-Concepts-and-Final-Challenge.md
|   |   |-- Trainer-Evaluation-Checklist.md
|   |-- Day2/
|       |-- Lab-00-Legacy-Solution-Setup.md
|       |-- Lab-01-Legacy-Analysis-and-Modernization-Planning.md
|       |-- Lab-02-Characterization-Tests-and-Safe-Refactoring.md
|       |-- Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md
|       |-- Lab-04-Security-Review-and-Remediation.md
|       |-- Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md
|       |-- Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md
|       |-- Trainer-Evaluation-Checklist.md
|-- References/
    |-- 01 - Claude-AI-and-AI-Assisted-Development.pdf
    |-- 02 - .NET-Modernization-Quality-Security-and-Automated-Testing.pdf
```

Lab solutions themselves are created during the exercises (`claude-dotnet-day1` / `claude-dotnet-day2`) and are not stored in this repository.

---

## How to Use This Repository

1. Open the [two-day table of contents](#two-day-training-table-of-contents) and locate the current session.
2. Open the matching [reference deck](#references) for that day.
3. Complete the linked lab in order. Start each day with Lab 00.
4. Trainers use the [evaluation checklists](#trainer-resources) against the listed deliverables.

Do not begin a lab with “implement this.” Analyze, design, and plan tests first.

---

## Engineering Principles

1. **Understand before changing.** Do not ask AI to rewrite code immediately.
2. **Context matters.** Provide relevant, accurate engineering context only.
3. **Plan before implementation.** Separate analysis and design from code generation.
4. **Validate AI output.** Generated code is a proposal until it is reviewed and tested.
5. **Test business behaviour.** Avoid testing implementation details unnecessarily.
6. **Diagnose before fixing.** Find the root cause instead of changing code blindly.
7. **Modernize incrementally.** Avoid full rewrites unless there is a strong business case.
8. **Security is part of engineering.** Include security review in the normal lifecycle.
9. **Use human approval for high-impact actions.** Especially destructive or irreversible tool calls.
10. **AI augments engineering discipline.** It does not replace architecture, testing, security, governance, or accountability.

---

## Expected Deliverables

By the end of the program, participants should have worked with:

- Order Management sample solution (Day 1)
- Legacy Loan Processing sample solution (Day 2)
- Reusable prompt templates for review, security, and test matrices
- Claude-enabled .NET API example, inventory tool-calling, and an agentic workflow
- MCP vs RAG classification and a conceptual MCP architecture
- Modernization assessment and characterization tests
- xUnit, NUnit, mock-based, and regression tests
- Security review and remediation
- Day 1 challenge and Day 2 testing capstone, each with a PR summary

---

## Program Goal

> **Use Claude to accelerate engineering while preserving software quality, security, maintainability, testability, governance, and human accountability.**
