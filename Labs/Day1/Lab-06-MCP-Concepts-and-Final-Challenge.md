# Lab 06 - MCP Concepts and Final Day 1 Challenge

## Lab Name
MCP Integration Thinking and End-to-End AI-Assisted Feature Delivery

## Description
This lab introduces MCP concepts and closes Day 1 with an integrated feature challenge that requires disciplined AI-assisted engineering from analysis through validation.

## Prerequisites
- Completion of Labs 00-05
- Familiarity with enterprise tooling (issue tracker, docs, APIs)

## Technology Used
- MCP concepts (tool standardization)
- RAG vs tool access decisioning
- End-to-end software delivery workflow

## Business Use Case / Scenario
Developers need Claude Code to implement a user story and validate real business rules using repository code plus enterprise systems.

## Conceptual Architecture

```text
Claude Code
      |
      v
     MCP
      |
 +----+---------+----------+
 |              |          |
Jira        Inventory   Documentation
 |              |          |
Story          API       Knowledge
```

## Step-by-Step Details

### Step 1 - Define candidate MCP tools

For Order Management:
- get_jira_story
- get_inventory
- search_architecture_docs
- get_customer

### Step 2 - RAG vs MCP classification exercise

Requirement: Find coding standard for CancellationToken.
Classification: RAG / knowledge retrieval

Requirement: Get inventory for P1001.
Classification: Tool / MCP

Requirement: Read Jira ORD-245.
Classification: Tool / MCP

Requirement: Find cancellation process documentation.
Classification: RAG / knowledge retrieval

Key memory:

```text
RAG = Knowledge
MCP = Tools / Systems / Actions
```

## Final Day 1 Challenge

### Challenge Requirement
Add an order eligibility rule:

```text
Orders over 25,000 require a manual approval flag before processing.
```

### Required Delivery Workflow
Participants must use Claude to perform:
1. Repository analysis
2. Requirement analysis
3. Impact analysis
4. Test matrix creation
5. Design proposal
6. Implementation
7. Code review
8. Automated tests
9. Debugging if required
10. Documentation
11. PR summary

### Mandatory Process Constraint
Do not start with: Implement this requirement.

Use this sequence:

```text
UNDERSTAND
 -> DESIGN
 -> TEST PLAN
 -> IMPLEMENT
 -> REVIEW
 -> TEST
 -> VALIDATE
```

### Expected Business Rule Clarifications
Participants should explicitly address:
- Does exactly 25,000 require approval?
- Can approval status be changed later?
- Who can approve?
- Should inventory be reserved before approval?
- Does discount apply before or after threshold check?

The challenge intentionally contains ambiguity to force requirement discovery.

## Expected Output
- Participants apply end-to-end disciplined AI workflow
- Manual approval rule implemented with validated behavior
- Open requirement questions captured explicitly
- Final code, tests, and documentation delivered

## Conclusion
MCP thinking and structured engineering workflow turn AI from a code generator into a reliable delivery accelerator for senior teams.