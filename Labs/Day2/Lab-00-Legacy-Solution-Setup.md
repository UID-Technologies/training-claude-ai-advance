# Lab 00 - Legacy Solution Setup

## Lab Name
Create the Legacy Loan Processing Baseline Application

## Description
This lab sets up a deliberately imperfect .NET solution that will be analyzed and modernized throughout Day 2.

## Prerequisites
- .NET SDK
- Visual Studio, VS Code, or Rider
- Git
- Terminal or PowerShell

## Technology Used
- .NET CLI
- ASP.NET Core Web API template
- C# class libraries
- xUnit template
- Git

## Business Use Case / Scenario
Your organization has a legacy internal Loan Processing Platform with mixed responsibilities and limited testability. The team needs a realistic baseline for modernization training.

## Folder Structure

```text
LegacyLoanProcessing
|
|-- src
|   |-- LegacyLoan.Api
|   |-- LegacyLoan.Services
|   |-- LegacyLoan.Data
|   |-- LegacyLoan.Domain
|
|-- tests
|   |-- LegacyLoan.Tests
```

## Setup Project

### Step 1 - Create workspace

```bash
mkdir claude-dotnet-day2
cd claude-dotnet-day2
```

### Step 2 - Create solution

```bash
dotnet new sln -n LegacyLoanProcessing
```

### Step 3 - Create projects

```bash
mkdir src
mkdir tests

dotnet new webapi -o src/LegacyLoan.Api
dotnet new classlib -o src/LegacyLoan.Services
dotnet new classlib -o src/LegacyLoan.Data
dotnet new classlib -o src/LegacyLoan.Domain
dotnet new xunit -o tests/LegacyLoan.Tests
```

### Step 4 - Add projects to solution

```bash
dotnet sln add src/LegacyLoan.Api
dotnet sln add src/LegacyLoan.Services
dotnet sln add src/LegacyLoan.Data
dotnet sln add src/LegacyLoan.Domain
dotnet sln add tests/LegacyLoan.Tests
```

### Step 5 - Add references

Services depends on Domain and Data:

```bash
dotnet add src/LegacyLoan.Services reference src/LegacyLoan.Domain
dotnet add src/LegacyLoan.Services reference src/LegacyLoan.Data
```

API depends on Services:

```bash
dotnet add src/LegacyLoan.Api reference src/LegacyLoan.Services
```

Tests depend on Services and Domain:

```bash
dotnet add tests/LegacyLoan.Tests reference src/LegacyLoan.Services
dotnet add tests/LegacyLoan.Tests reference src/LegacyLoan.Domain
```

### Step 6 - Create domain model

Create src/LegacyLoan.Domain/LoanApplication.cs:

```csharp
namespace LegacyLoan.Domain;

public class LoanApplication
{
    public int Id { get; set; }
    public int CustomerId { get; set; }
    public decimal Amount { get; set; }
    public int CreditScore { get; set; }
    public string Status { get; set; } = string.Empty;
    public DateTime CreatedOn { get; set; }
}
```

### Step 7 - Create deliberately legacy service

Create src/LegacyLoan.Services/LoanService.cs:

```csharp
using LegacyLoan.Domain;

namespace LegacyLoan.Services;

public class LoanService
{
    public LoanApplication ProcessLoan(
        int customerId,
        decimal amount,
        int creditScore)
    {
        if (customerId == 0)
            throw new Exception("Invalid customer");

        if (amount < 0)
            throw new Exception("Invalid amount");

        var loan = new LoanApplication();

        loan.Id = new Random().Next(1, 100000);
        loan.CustomerId = customerId;
        loan.Amount = amount;
        loan.CreditScore = creditScore;
        loan.CreatedOn = DateTime.Now;

        if (creditScore > 650)
        {
            if (amount < 500000)
            {
                loan.Status = "Approved";
            }
            else
            {
                loan.Status = "ManualReview";
            }
        }
        else
        {
            loan.Status = "Rejected";
        }

        Console.WriteLine("Loan created for customer " + customerId);

        return loan;
    }
}
```

### Step 8 - Build and commit baseline

```bash
dotnet build
git init
dotnet new gitignore
git add .
git commit -m "Initial legacy loan processing application"
```

## Expected Output
- Solution and all projects are created successfully
- Baseline legacy service compiles
- Build succeeds
- Baseline commit is available

## Conclusion
You now have a realistic legacy application baseline required for analysis, refactoring, testing, and secure modernization workflows.