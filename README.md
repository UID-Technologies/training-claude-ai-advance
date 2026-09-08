# Claude AI for .NET Developers
## 2-Day Hands-on Training Program

This repository contains the training content, hands-on labs, sample code, and supporting material for a two-day intermediate-level program focused on using Claude AI across the .NET software development lifecycle.

The program is designed for experienced .NET developers, senior developers, technical leads, and solution architects who want to use Claude for software engineering rather than only for general-purpose chat or basic code generation.

---

## Quick Navigation

- Day 1 index: [Day 1/Lab.md](Day%201/Lab.md)
- Day 2 index: [Day 2/Lab.md](Day%202/Lab.md)
- Day 1 trainer checklist: [Day 1/Trainer-Evaluation-Checklist.md](Day%201/Trainer-Evaluation-Checklist.md)
- Day 2 trainer checklist: [Day 2/Trainer-Evaluation-Checklist.md](Day%202/Trainer-Evaluation-Checklist.md)

---

## Program Overview

### Day 1 – Claude AI & AI-Assisted Development

Day 1 focuses on understanding the Claude platform, writing effective prompts for software engineering, using Claude Code for repository-level development, and introducing tool use, MCP, RAG, and agentic development patterns.

The central theme is:

```text
Requirement
   ↓
Understand
   ↓
Design
   ↓
Code
   ↓
Review
   ↓
Test
   ↓
Debug
   ↓
Document
   ↓
Human Approval
```

### Day 2 – .NET Modernization, Quality, Security & Automated Testing

Day 2 focuses on using Claude to understand and modernize legacy .NET applications, improve code quality, detect and remediate defects, review security risks, and create automated tests using xUnit, NUnit, and mocking.

The central theme is:

```text
Legacy Application
      ↓
Analyze
      ↓
Identify Technical Debt
      ↓
Plan
      ↓
Refactor
      ↓
Secure
      ↓
Test
      ↓
Validate
```

---

# Target Audience

This program is suitable for:

- .NET Developers
- Senior .NET Developers
- Full Stack Developers working with .NET
- Technical Leads
- Solution Architects
- Engineering Leads
- Application Modernization Teams
- Developers evaluating AI-assisted engineering practices

---

# Recommended Experience

Participants should already be familiar with:

- C#
- .NET / ASP.NET Core
- Object-oriented programming
- REST APIs
- Dependency Injection
- Async programming
- Git
- Basic software architecture
- Basic unit testing concepts

This is not an introductory C# or .NET training program.

---

# Technology Stack

The training uses or discusses:

- .NET
- ASP.NET Core
- C#
- Entity Framework Core
- REST APIs
- Git
- Claude
- Claude Code
- Anthropic API concepts
- Tool Use / Function Calling
- MCP
- RAG
- xUnit
- NUnit
- Moq
- Postman or `.http` files
- Visual Studio / Visual Studio Code / Rider

---

# Learning Objectives

By the end of the two-day program, participants should be able to:

- Understand the Claude platform and model ecosystem
- Select models based on task complexity, cost, and performance
- Understand context windows and token usage
- Apply context-management strategies to large repositories
- Integrate Claude into .NET development workflows
- Write effective structured prompts for engineering tasks
- Use Claude for code explanation, generation, debugging, and review
- Use Claude Code to understand and modify an existing repository
- Apply Claude across the full development lifecycle
- Understand tool use and function calling
- Understand MCP and enterprise tool integration
- Understand where RAG fits into enterprise AI solutions
- Design simple agentic development workflows
- Analyze and modernize legacy .NET applications
- Identify and prioritize technical debt
- Refactor legacy C# code safely
- Review AI-generated code before acceptance
- Perform AI-assisted bug detection and root-cause analysis
- Perform secure coding and AI-assisted security reviews
- Create meaningful automated test strategies
- Write unit tests using xUnit and NUnit
- Mock repositories and external services
- Create regression tests for resolved defects
- Validate AI-generated changes before production acceptance

---

# Repository Structure

Current workspace structure:

```text
training-claude-ai-advance/
|
|-- README.md
|-- Day 1/
|   |-- Lab.md
|   |-- Lab-00-Base-Solution-Setup.md
|   |-- Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md
|   |-- Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md
|   |-- Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md
|   |-- Lab-04-Claude-Enabled-API-Code-Review-Service.md
|   |-- Lab-05-Tool-Use-and-Agentic-Workflow.md
|   |-- Lab-06-MCP-Concepts-and-Final-Challenge.md
|   |-- Trainer-Evaluation-Checklist.md
|
|-- Day 2/
|   |-- Lab.md
|   |-- Lab-00-Legacy-Solution-Setup.md
|   |-- Lab-01-Legacy-Analysis-and-Modernization-Planning.md
|   |-- Lab-02-Characterization-Tests-and-Safe-Refactoring.md
|   |-- Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md
|   |-- Lab-04-Security-Review-and-Remediation.md
|   |-- Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md
|   |-- Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md
|   |-- Trainer-Evaluation-Checklist.md
```

| Path | Purpose |
|---|---|
| Day 1/Lab.md | Day 1 master index and delivery sequence |
| Day 1/Lab-00-... to Lab-06-... | Day 1 modular hands-on labs |
| Day 1/Trainer-Evaluation-Checklist.md | Day 1 trainer rubric and outcomes |
| Day 2/Lab.md | Day 2 master index and delivery sequence |
| Day 2/Lab-00-... to Lab-06-... | Day 2 modular hands-on labs |
| Day 2/Trainer-Evaluation-Checklist.md | Day 2 trainer rubric and outcomes |

---

# Day 1 – Claude AI & AI-Assisted Development

## Day 1 Objective

Day 1 introduces Claude as an engineering assistant that can work across the software development lifecycle.

The objective is not simply to generate code.

Participants learn to use Claude through a controlled engineering workflow:

```text
Understand
   ↓
Design
   ↓
Generate
   ↓
Review
   ↓
Test
   ↓
Debug
   ↓
Validate
```

---

## Module 1 – Claude Platform & Model Overview

### Topics

- Claude model family and capabilities
- Model selection considerations
- Model selection for development tasks
- Claude Platform / Console overview
- API authentication and key management
- Context windows and token fundamentals
- Context-window management for large repositories
- Cost and performance considerations
- Claude limitations
- Validation requirements
- Claude SDK / API overview
- Fable model overview and use cases
- Cowork overview and use cases

### Key Concepts

#### Claude as a Development Platform

Claude can support:

- Code explanation
- Code generation
- Debugging
- Code review
- Architecture analysis
- Refactoring
- Test generation
- Documentation
- Repository analysis
- Tool interaction
- Agentic workflows

#### Model Selection

Model selection should consider:

- Task complexity
- Context size
- Response latency
- Cost
- Required reasoning depth
- Coding complexity
- Tool usage
- Agentic behaviour

The most powerful model should not automatically be used for every task.

#### Context Management

For large repositories, use progressive discovery:

```text
Repository
   ↓
Understand Structure
   ↓
Identify Feature
   ↓
Identify Relevant Files
   ↓
Trace Dependencies
   ↓
Perform Task
```

#### AI Validation Principle

AI-generated code should be treated as a proposal until validated through:

```text
Developer Review
   ↓
Build
   ↓
Static Analysis
   ↓
Unit Tests
   ↓
Integration Tests
   ↓
Security Validation
   ↓
PR Review
```

---

## Day 1 Demo – Claude Code Explanation & Generation

The demo introduces a C# business method and uses Claude to:

- Explain current behaviour
- Discover hidden business rules
- Identify assumptions
- Identify maintainability issues
- Recommend improvements
- Generate tests

The important workflow is:

```text
Understand → Analyze → Improve → Test
```

---

# Module 2 – Prompt Engineering for Developers

## Topics

- System prompts vs. user prompts
- Structured prompting
- Context-aware prompting
- Few-shot prompting
- Effective software-engineering prompts
- Code generation prompts
- Debugging prompts
- Code-review prompts
- Test-generation prompts
- Test-case discovery
- Legacy-code analysis prompts
- Architecture-review prompts
- Security-review prompts
- Test-matrix generation
- Refactoring prompts

---

## Recommended Developer Prompt Pattern

A consistent prompt pattern is used throughout the training:

```text
Role
  ↓
Context
  ↓
Task
  ↓
Constraints
  ↓
Expected Output
```

### Example

```text
Role:
Act as a senior .NET solution architect.

Context:
This is an ASP.NET Core Order Management API using
Entity Framework Core and SQL Server.

Task:
Review CreateOrderAsync.

Constraints:
- Preserve public API
- Do not add new packages
- Use async APIs
- Do not change unrelated code

Expected Output:
- Findings
- Severity
- Reason
- Recommendation
```

---

## System Prompt vs. User Prompt

### System Prompt

Defines persistent behaviour.

Example:

```text
You are a senior .NET engineer.
Prefer maintainable solutions.
Preserve public contracts.
Identify assumptions.
Consider security and testability.
```

### User Prompt

Defines the immediate task.

Example:

```text
Review CreateOrderAsync for concurrency and
error-handling issues.
```

---

## Context-Aware Prompting

Better prompts include:

- Framework
- Runtime
- Scale
- Architecture
- Database
- Business rules
- Performance requirements
- Existing constraints

Instead of:

```text
Optimize this query.
```

Prefer:

```text
This EF Core query runs against SQL Server.
The Orders table contains approximately
15 million rows and only the latest 100
orders are required.
```

---

## Test-Generation Prompting

Do not begin with:

```text
Generate unit tests.
```

Recommended workflow:

```text
Analyze Code
   ↓
Identify Business Rules
   ↓
Generate Test Matrix
   ↓
Review Matrix
   ↓
Generate Tests
```

---

## Lab 1 – Prompt Engineering for Software Developers

Participants create prompts for:

- Code explanation
- Code review
- Refactoring
- Test-case discovery
- Security review

using:

```text
Role → Context → Task → Constraints → Expected Output
```

---

# Module 3 – Claude Code & Developer Productivity

## Topics

- Introduction to Claude Code
- Development environment setup
- Understanding existing codebases
- Repository-level context
- Code generation
- Code modification
- Refactoring
- Code explanation
- Documentation
- Skills-based development practices
- Reusable development instructions
- Test generation
- Feature development
- Pull-request assistance
- Code-review support

---

## Claude Across the Development Lifecycle

```text
Requirement
    ↓
Understand
    ↓
Design
    ↓
Code
    ↓
Review
    ↓
Test
    ↓
Debug
    ↓
Document
    ↓
Pull Request
```

---

## Repository Understanding

A good initial Claude Code task is:

```text
Analyze this repository.
Do not modify files.

Explain:
- Projects
- Architecture
- Dependencies
- Domain
- Database access
- Tests
- Main execution flows
```

The principle is:

**Understand before changing.**

---

## Feature Development Workflow

```text
Understand Requirement
       ↓
Locate Relevant Code
       ↓
Impact Analysis
       ↓
Design
       ↓
Developer Review
       ↓
Implementation
       ↓
Code Review
       ↓
Tests
       ↓
Documentation
       ↓
PR
```

---

## Reusable Repository Instructions

Teams can define reusable AI development rules such as:

### Architecture

- Keep controllers thin
- Follow dependency inversion
- Respect application/domain boundaries

### Coding

- Prefer async APIs
- Support `CancellationToken`
- Use nullable reference types

### Testing

- Use xUnit
- Use Moq where dependencies require isolation
- Follow Arrange / Act / Assert

### Security

- Never log secrets
- Do not hard-code credentials
- Protect sensitive customer data

---

## Lab 2 – Claude Code Existing Project Enhancement

Participants use Claude Code to:

- Analyze an existing solution
- Trace a business flow
- Design a change
- Implement a small feature
- Refactor selected code
- Generate tests
- Generate documentation
- Prepare a PR summary

---

# Module 4 – Tool Use, MCP & Agentic Development

## Topics

- Tool use
- Function calling
- Tool schemas
- Agentic development concepts
- Multi-step workflows
- MCP fundamentals
- Connecting Claude with internal tools and APIs
- RAG overview
- Enterprise knowledge integration

---

## Tool Use

Claude should use external tools when it needs authoritative or live data.

Example:

```text
User:
How much inventory exists for product P1001?

Claude:
Needs current inventory.

Tool:
get_inventory("P1001")

Inventory API:
10

Claude:
P1001 currently has 10 units available.
```

---

## Agentic Workflow

Traditional interaction:

```text
Prompt → Response
```

Agentic interaction:

```text
Goal
  ↓
Reason
  ↓
Select Tool
  ↓
Execute Tool
  ↓
Observe Result
  ↓
Reason Again
  ↓
Next Action
```

Recommended mental model:

```text
Goal → Reason → Tool → Result → Next Action
```

---

## MCP

MCP provides a standardized model for connecting Claude with external systems.

Conceptually:

```text
Claude
  |
  v
 MCP
  |
  +------------------------+
  |       |       |        |
 GitHub  Jira   Database  APIs
```

Possible enterprise tools include:

- `get_jira_story`
- `get_customer`
- `get_order`
- `get_inventory`
- `search_documentation`
- `search_logs`
- `query_metrics`

---

## RAG vs. MCP

### RAG

Answers:

**What information should Claude know?**

Examples:

- Retrieve coding standards
- Retrieve API documentation
- Search policies
- Search architecture documentation

### MCP / Tools

Answers:

**What systems should Claude interact with?**

Examples:

- Query Jira
- Check inventory
- Create a ticket
- Call an internal API

Easy memory:

```text
RAG = Knowledge

MCP = Tools / Systems / Actions
```

---

## Lab 3 – Tool Use, MCP & Agentic Workflow

Participants demonstrate:

```text
Goal
  ↓
Reason
  ↓
Tool
  ↓
Result
  ↓
Next Action
```

using an Order Management and Inventory scenario.

---

# Day 1 Hands-on Labs

Day 1 is now organized into modular lab files:

1. [Day 1/Lab-00-Base-Solution-Setup.md](Day%201/Lab-00-Base-Solution-Setup.md)
2. [Day 1/Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md](Day%201/Lab-01-Claude-Analysis-Prompting-and-Test-Matrix.md)
3. [Day 1/Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md](Day%201/Lab-02-Repository-Understanding-and-AI-Assisted-Feature-Development.md)
4. [Day 1/Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md](Day%201/Lab-03-Regression-Testing-and-AI-Assisted-Debugging.md)
5. [Day 1/Lab-04-Claude-Enabled-API-Code-Review-Service.md](Day%201/Lab-04-Claude-Enabled-API-Code-Review-Service.md)
6. [Day 1/Lab-05-Tool-Use-and-Agentic-Workflow.md](Day%201/Lab-05-Tool-Use-and-Agentic-Workflow.md)
7. [Day 1/Lab-06-MCP-Concepts-and-Final-Challenge.md](Day%201/Lab-06-MCP-Concepts-and-Final-Challenge.md)
8. [Day 1/Trainer-Evaluation-Checklist.md](Day%201/Trainer-Evaluation-Checklist.md)

---

# Day 1 Business Scenario

The Day 1 labs use an enterprise-style **Order Fulfillment Platform**.

Core flow:

```text
Customer
   ↓
Order
   ↓
Order Items
   ↓
Inventory
   ↓
Payment / Processing
```

Order creation includes:

- Customer validation
- Item validation
- Inventory validation
- Total calculation
- Discount rules
- Persistence
- Order-number generation

---

# Day 1 Expected Outcomes

Participants should be able to:

- Write stronger development prompts
- Scope Claude to relevant repository context
- Use Claude Code without blindly modifying code
- Use AI for impact analysis
- Generate and review test matrices
- Use AI for debugging
- Integrate Claude into a .NET API
- Understand tools, MCP, RAG, and agentic flows
- Validate AI-generated changes before approval

---

# Day 2 – .NET Modernization, Quality, Security & Automated Testing

## Day 2 Objective

Day 2 shifts focus from AI-assisted feature development to AI-assisted modernization and quality assurance.

Participants learn to improve an existing .NET application without unnecessarily rewriting it.

Main workflow:

```text
Understand
   ↓
Identify Risk
   ↓
Create Safety Tests
   ↓
Modernize
   ↓
Review
   ↓
Secure
   ↓
Test
   ↓
Validate
```

---

# Module 5 – Legacy .NET Modernization with Claude

## Topics

- Understanding legacy .NET applications
- Analyzing project structure and dependencies
- Identifying technical debt
- Identifying outdated coding patterns
- Finding modernization opportunities
- Creating an AI-assisted modernization plan
- Refactoring legacy C# code
- Improving maintainability
- Modernizing selected components
- Validating AI-generated changes
- Security risks
- Testability
- Performance concerns

---

## Legacy Application Characteristics

Common legacy characteristics include:

- Older .NET versions
- Large monolithic solutions
- Limited tests
- Tight coupling
- Static dependencies
- Hard-coded configuration
- Direct database access
- Synchronous I/O
- Mixed application and infrastructure logic
- Outdated libraries
- Difficult deployment processes

Legacy is primarily about **change risk and maintainability**, not simply code age.

---

## Technical Debt

Claude can assist with identifying:

- Duplicate code
- Long methods
- God classes
- Static state
- Tight coupling
- Deep inheritance
- Poor naming
- Hard-coded values
- Dead code
- Missing tests
- Outdated dependencies
- Hidden business rules

Recommended output:

```text
Problem
   ↓
Impact
   ↓
Risk
   ↓
Recommended Improvement
```

---

## Modernization Prioritization

```text
High Business Impact + High Risk
        ↓
Modernize First

High Business Impact + Low Risk
        ↓
Strategic Improvement

Low Business Impact + High Risk
        ↓
Contain / Isolate

Low Business Impact + Low Risk
        ↓
Defer
```

---

## Modernization Workflow

```text
Legacy Application
      ↓
Analyze
      ↓
Identify Technical Debt
      ↓
Prioritize
      ↓
Modernization Plan
      ↓
Characterization Tests
      ↓
Refactor
      ↓
Build
      ↓
Test
      ↓
Validate
```

---

## Characterization Testing

Before risky refactoring:

```text
Observe Existing Behaviour
      ↓
Create Tests
      ↓
Refactor
      ↓
Run Same Tests
```

This helps preserve behaviour even when legacy requirements are poorly documented.

---

## Lab 1 – Legacy .NET Modernization with Claude

Participants:

- Analyze the legacy application
- Identify technical debt
- Categorize findings
- Create a modernization plan
- Add characterization tests
- Refactor a selected component
- Validate the changes

---

# Module 6 – Code Quality, Bug Detection & Secure Coding

## Code Quality Topics

- AI-assisted code review
- Code-smell identification
- Complexity detection
- Duplication detection
- Refactoring recommendations
- Readability
- Maintainability
- Reviewing AI-generated code before acceptance

---

## Common Code Smells

Examples include:

- Long Method
- Large Class
- Duplicate Code
- Deep Nesting
- Primitive Obsession
- Too Many Parameters
- Feature Envy
- Tight Coupling
- Global State

A code smell is not automatically a defect.

It is a signal that deeper analysis may be required.

---

## Bug Detection & Remediation

Topics include:

- Error analysis
- Stack-trace analysis
- Root-cause analysis
- Defect identification
- Minimal remediation
- Regression tests
- Validation

Recommended process:

```text
Observed Problem
      ↓
Collect Evidence
      ↓
Reproduce
      ↓
Root Cause
      ↓
Minimal Fix
      ↓
Regression Test
      ↓
Validate
```

---

## Root-Cause Analysis Prompt Structure

Provide:

- Observed behaviour
- Expected behaviour
- Error message
- Stack trace
- Request or input
- Relevant code
- Environment information

Ask Claude for:

1. Possible hypotheses
2. Evidence required
3. Diagnostic steps
4. Most probable root cause
5. Minimal remediation

---

## Regression Testing

```text
Bug
  ↓
Reproduce with Test
  ↓
Test Fails
  ↓
Apply Fix
  ↓
Test Passes
  ↓
Keep Test
```

---

# Secure Coding

## Topics

- Secure coding practices
- AI-assisted security review
- Input validation
- SQL injection
- Hard-coded secrets
- Authentication
- Authorization
- Sensitive-data exposure
- Error handling
- Secure logging
- Reviewing AI-generated code for vulnerabilities
- Security remediation

---

## Security Review Areas

Claude can be instructed to inspect:

- Trust boundaries
- User-controlled input
- Authentication
- Authorization
- Database operations
- External API calls
- Secret handling
- Logging
- Error handling
- Sensitive data

Recommended output:

```text
Severity
   ↓
Vulnerability
   ↓
Exploit Scenario
   ↓
Impact
   ↓
Recommendation
```

---

## Secure Secret Management

Do not hard-code:

- API keys
- Passwords
- Tokens
- Database credentials
- Certificates

Use:

- Environment variables
- .NET User Secrets for development
- Azure Key Vault
- AWS Secrets Manager
- Enterprise secret-management platforms

---

## Authentication vs. Authorization

### Authentication

```text
Who are you?
```

### Authorization

```text
What are you allowed to do?
```

A common vulnerability is authenticating a caller but failing to check whether they are allowed to access a specific resource.

---

## Lab 2 – Code Quality, Bug Remediation & Secure Coding

Participants:

```text
Analyze
  ↓
Find Bug
  ↓
Root Cause
  ↓
Fix
  ↓
Security Review
  ↓
Regression Test
  ↓
Validate
```

---

# Module 7 – .NET Unit Testing with xUnit & NUnit

## Why Automated Testing Matters

Automated testing provides a safety net for:

- AI-generated code
- Refactoring
- Legacy modernization
- Bug fixes
- Security remediation
- CI/CD pipelines

Tests help:

- Verify business rules
- Detect regressions
- Reproduce defects
- Validate boundary conditions
- Support quality gates

---

# AI-Assisted Testing Workflow

```text
Understand Requirement
        ↓
Identify Scenarios
        ↓
Generate Test Matrix
        ↓
Review Matrix
        ↓
Generate Tests
        ↓
Run
        ↓
Analyze Failure
        ↓
Fix
        ↓
Regression Validation
```

---

# xUnit Fundamentals

Topics include:

- Creating xUnit projects
- Test-project structure
- Naming conventions
- `[Fact]`
- `[Theory]`
- `[InlineData]`
- Arrange / Act / Assert
- Assertions
- Exception testing
- Positive scenarios
- Negative scenarios
- Boundary scenarios
- Async unit tests

Example:

```csharp
[Fact]
public void CalculateInterest_ShouldReturnExpectedValue()
{
    // Arrange

    // Act

    // Assert
}
```

Parameterized example:

```csharp
[Theory]
[InlineData(1000, 10, 100)]
[InlineData(2000, 10, 200)]
public void CalculateInterest_ShouldReturnExpectedValue(
    decimal amount,
    decimal rate,
    decimal expected)
{
    // Test implementation
}
```

---

# NUnit Fundamentals

Topics include:

- Creating NUnit projects
- `[Test]`
- `[TestCase]`
- `[SetUp]`
- `[TearDown]`
- Assertions
- Exception testing
- Parameterized tests
- Async tests
- Organizing fixtures

---

# xUnit vs. NUnit

| Area | xUnit | NUnit |
|---|---|---|
| Basic test | `[Fact]` | `[Test]` |
| Parameterized test | `[Theory]` + `[InlineData]` | `[TestCase]` |
| Setup | Constructor / fixtures | `[SetUp]` |
| Cleanup | `IDisposable` / fixtures | `[TearDown]` |
| Async tests | Supported | Supported |
| Typical positioning | Common in modern .NET projects | Mature and widely adopted |

The goal is not to declare one framework universally better.

Participants should be comfortable working with whichever framework the project or client uses.

---

# Test Matrix First

Instead of:

```text
Generate tests.
```

Use:

```text
Analyze Code
   ↓
Identify Business Rules
   ↓
Generate Test Matrix
   ↓
Developer Review
   ↓
Generate Tests
```

Typical scenarios include:

- Happy path
- Null input
- Missing input
- Invalid values
- Exact boundary values
- Exceptions
- Dependency failures
- Timeouts
- Cancellation
- Duplicate requests
- Authorization

---

# Mocking Dependencies

Typical LoanService dependencies:

```text
LoanService
   |
   +------ ICustomerRepository
   |
   +------ ICreditScoreService
   |
   +------ INotificationService
```

Unit tests replace external dependencies with controlled mocks.

Mocking allows developers to test:

- Dependency success
- Missing data
- External service failure
- Timeout
- Exceptional paths
- Interaction requirements

Avoid excessive mocking of implementation details.

---

# Running Tests

Typical command:

```bash
dotnet test
```

Testing workflow:

```text
Build
  ↓
Discover Tests
  ↓
Execute
  ↓
Analyze Results
  ↓
Pass / Fail
```

CI/CD systems can use test failures to block:

- Pull-request merges
- Deployments
- Release promotion

---

# Diagnosing Failing Tests with Claude

Provide Claude:

- Failing test
- Test name
- Expected result
- Actual result
- Stack trace
- Relevant code
- Business rule

Ask Claude whether the failure represents:

1. Production-code defect
2. Incorrect test expectation
3. Incorrect mock setup
4. Ambiguous requirement
5. Environment issue

The principle is:

**Diagnose first. Fix second.**

---

## Lab 3 – AI-Assisted Unit Testing with xUnit & NUnit

Participants:

- Analyze a .NET service
- Identify business rules
- Create a test matrix
- Generate xUnit tests
- Introduce mocking
- Run tests
- Analyze failures
- Convert selected tests to NUnit
- Create regression tests
- Review test coverage gaps

---

# Day 2 Hands-on Labs

Day 2 is now organized into modular lab files:

1. [Day 2/Lab-00-Legacy-Solution-Setup.md](Day%202/Lab-00-Legacy-Solution-Setup.md)
2. [Day 2/Lab-01-Legacy-Analysis-and-Modernization-Planning.md](Day%202/Lab-01-Legacy-Analysis-and-Modernization-Planning.md)
3. [Day 2/Lab-02-Characterization-Tests-and-Safe-Refactoring.md](Day%202/Lab-02-Characterization-Tests-and-Safe-Refactoring.md)
4. [Day 2/Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md](Day%202/Lab-03-Code-Quality-Bug-Analysis-and-Regression-Workflow.md)
5. [Day 2/Lab-04-Security-Review-and-Remediation.md](Day%202/Lab-04-Security-Review-and-Remediation.md)
6. [Day 2/Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md](Day%202/Lab-05-xUnit-NUnit-and-Mocking-Dependencies.md)
7. [Day 2/Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md](Day%202/Lab-06-Failing-Test-Diagnosis-Test-Gap-Review-and-Capstone.md)
8. [Day 2/Trainer-Evaluation-Checklist.md](Day%202/Trainer-Evaluation-Checklist.md)

---

# Day 2 Business Scenario

The Day 2 labs use a **Legacy Loan Processing Platform**.

Core flow:

```text
Customer
   ↓
Loan Application
   ↓
Eligibility Rules
   ↓
Credit Score
   ↓
Loan Decision
   ↓
Notification
```

Typical legacy problems include:

- Generic exceptions
- Hard-coded thresholds
- String-based statuses
- Console logging
- Tight coupling
- Hidden dependencies
- Poor testability
- Weak validation
- Security issues
- Limited unit tests

---

# Day 2 Testing-Focused Capstone

A new business policy is introduced:

> Loans above ₹750,000 require both a credit score of at least 700 and manual approval.

Participants must:

1. Analyze the requirement
2. Identify ambiguous boundaries
3. Analyze affected code
4. Create a test matrix
5. Add tests before implementation
6. Implement the smallest safe change
7. Run the full test suite
8. Perform code review
9. Perform security review
10. Validate regression behaviour
11. Prepare a PR summary

---

# Complete Two-Day Learning Journey

```text
DAY 1
AI-Assisted Development
        ↓
Prompt Engineering
        ↓
Repository Understanding
        ↓
Feature Development
        ↓
Tool Use
        ↓
Agentic Workflows
        ↓

DAY 2
Legacy Analysis
        ↓
Modernization
        ↓
Code Quality
        ↓
Bug Remediation
        ↓
Security
        ↓
Automated Testing
        ↓
Regression Validation
```

---

# Engineering Principles Reinforced Throughout

## 1. Understand Before Changing

Do not immediately ask AI to rewrite code.

## 2. Context Matters

Provide only relevant, accurate engineering context.

## 3. Plan Before Implementation

Separate analysis and design from code generation.

## 4. Validate AI Output

AI-generated code is a proposal until reviewed and tested.

## 5. Test Business Behaviour

Avoid testing implementation details unnecessarily.

## 6. Diagnose Before Fixing

Find the root cause instead of blindly changing code.

## 7. Modernize Incrementally

Avoid full rewrites unless there is a strong business case.

## 8. Security Is Part of Engineering

Security review belongs inside the normal development lifecycle.

## 9. Use Human Approval for Important Actions

Especially for destructive or high-impact agentic tool calls.

## 10. AI Augments Engineering Discipline

It does not replace architecture, testing, security, governance, or human accountability.

---

# Recommended Training Flow

## Day 1

### First Half

- Claude overview
- Models
- Context
- Prompt engineering
- Code explanation
- Code review
- Test discovery

### Second Half

- Claude Code
- Repository analysis
- Feature development
- Tool use
- Agentic workflow
- MCP / RAG overview

## Day 2

### First Half

- Legacy modernization
- Technical debt
- Code quality
- Bug detection
- Secure coding

### Second Half

- xUnit
- NUnit
- Mocking
- Failure analysis
- Regression tests
- Testing-focused capstone

---

# Suggested Lab Working Model

Participants can work:

- Individually
- In pairs
- In small development teams

Recommended pattern:

```text
Instructor Demo
     ↓
Participant Exercise
     ↓
Claude-Assisted Analysis
     ↓
Implementation
     ↓
Peer / AI Review
     ↓
Validation
     ↓
Trainer Discussion
```

---

# Expected Final Deliverables

By the end of the program, participants should have worked with:

- Order Management sample solution
- Legacy Loan Processing sample solution
- Reusable Claude prompt templates
- Code-review prompts
- Security-review prompts
- Test-matrix templates
- xUnit tests
- NUnit tests
- Mock-based tests
- Regression tests
- Claude-enabled .NET API example
- Inventory tool/function-calling example
- Agentic workflow example
- MCP conceptual architecture
- Modernization assessment
- PR summaries
- Capstone solution

---

# Final Program Message

The program does not teach developers to replace the software-development lifecycle with AI.

It teaches developers to insert AI intelligently into the lifecycle.

```text
Requirement
    ↓
Understand
    ↓
Plan
    ↓
Generate
    ↓
Review
    ↓
Secure
    ↓
Test
    ↓
Validate
    ↓
Human Decision
```

The goal is:

> **Use Claude to accelerate engineering while preserving software quality, security, maintainability, testability, governance, and human accountability.**
