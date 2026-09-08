# Lab 04 - Security Review and Remediation

## Lab Name
Practical Security Analysis of Legacy Data Access Code

## Description
This lab focuses on detecting common security issues in legacy code and implementing minimal secure remediation with re-validation.

## Prerequisites
- Completion of Labs 00-03
- Data project available

## Technology Used
- Secure coding review patterns
- Parameterization principles for SQL
- Secret management concepts

## Business Use Case / Scenario
A legacy repository component contains hard-coded credentials and query-string concatenation. The team must identify and remediate vulnerabilities before production exposure.

## Step-by-Step Details

### Step 1 - Add intentionally unsafe example

Create src/LegacyLoan.Data/CustomerRepository.cs:

```csharp
namespace LegacyLoan.Data;

public class CustomerRepository
{
    private readonly string _connectionString =
        "Server=prod-db;User Id=admin;Password=Password123;";

    public string GetCustomerQuery(string name)
    {
        return "SELECT * FROM Customers WHERE Name = '" +
               name + "'";
    }
}
```

### Step 2 - Run focused security review prompt

```text
Act as an application security engineer
reviewing a .NET application.

Review this code for:
- hard-coded secrets
- SQL injection
- input validation
- sensitive information
- logging risks
- error handling
- authentication / authorization implications

Expected Output:
Severity
Vulnerability
Attack Scenario
Impact
Recommended remediation

Do not rewrite code yet.
```

### Step 3 - Validate expected findings

Findings should include:
- Hard-coded credentials
- SQL injection via string concatenation
- Secret leakage risk in source control

### Step 4 - Define remediation principles

- Secrets in configuration or secret manager
- Parameterized SQL
- Input validation

### Step 5 - Request minimal secure change

```text
Make the smallest secure change.

Do not introduce unnecessary packages.
```

### Step 6 - Re-review remediated code

```text
Review the remediated code again.

Verify whether the original vulnerabilities
are actually resolved.
```

## Expected Output
- Vulnerabilities identified with clear attack scenarios
- Minimal secure remediation applied
- Follow-up review confirms remediation effectiveness

## Conclusion
Security work is a two-pass process: identify before change and verify after change.