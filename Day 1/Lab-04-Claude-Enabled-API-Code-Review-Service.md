# Lab 04 - Build a Claude-Enabled .NET API Code Review Service

## Lab Name
Secure Claude API Integration in ASP.NET Core

## Description
This lab introduces secure integration with Claude API by building an internal endpoint that reviews code snippets and returns structured findings.

## Prerequisites
- Completion of Labs 00-03
- Anthropic API access
- ASP.NET Core API project available
- Knowledge of secrets handling

## Technology Used
- ASP.NET Core minimal APIs or controllers
- .NET user-secrets
- Configuration system
- HTTP client or approved Claude SDK

## Business Use Case / Scenario
Internal engineering teams need a controlled API endpoint to request quick code quality feedback without exposing credentials or coupling business services directly to model calls.

## Folder Structure Context

```text
OrderManagement
|-- src
|   |-- OrderManagement.Api
|   |-- OrderManagement.Application
```

## Step-by-Step Details

### Step 1 - Configure API key securely

```bash
cd src/OrderManagement.Api
dotnet user-secrets init
dotnet user-secrets set "Anthropic:ApiKey" "YOUR_API_KEY"
```

Important: never commit API keys.

### Step 2 - Read configuration in Program.cs

Access key from configuration:

```csharp
var apiKey = builder.Configuration["Anthropic:ApiKey"];
```

Validate key exists before registering AI service.

### Step 3 - Create request contract

```csharp
public record CodeReviewRequest(
    string Code,
    string Language);
```

### Step 4 - Create service abstraction

```csharp
public interface IClaudeService
{
    Task<string> ReviewCodeAsync(
        string code,
        string language,
        CancellationToken cancellationToken);
}
```

### Step 5 - Design prompts

System prompt concept:

```text
You are a senior software engineer performing
production code reviews.

Focus on correctness, maintainability, security,
and testability.

Never invent missing application context.
Clearly state assumptions.
```

User prompt concept:

```text
Review this C# code.

Return:
- findings
- severity
- recommendation
```

### Step 6 - Call Claude Messages API

Use configured model, system, messages, and max token controls. Keep model names in configuration to avoid hard-coded identifiers.

### Step 7 - Add internal endpoint

Example endpoint:

```text
POST /api/ai/code-review
```

Sample request:

```json
{
  "language": "csharp",
  "code": "public void Process() { ... }"
}
```

Sample response:

```json
{
  "review": "..."
}
```

### Step 8 - Validate behavior

Use Postman or HTTP file tests. Provide intentionally problematic code and verify useful review output.

Example test snippet:

```csharp
public Customer GetCustomer(int id)
{
    var connection =
        new SqlConnection("hard-coded-connection");

    // ...
}
```

## Expected Output
- API key managed via user-secrets
- Claude service abstraction implemented
- Internal review endpoint working
- Responses contain structured review guidance

## Conclusion
Secure API integration requires separation of concerns, configuration-driven model settings, and disciplined prompt design.