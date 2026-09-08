# Lab 00 - Base Solution Setup

## Lab Name
Base .NET Solution Setup for Order Management

## Description
In this lab, participants create the baseline multi-project .NET solution used across all Day 1 labs. The focus is on creating a clean architecture foundation, project references, and source control baseline.

## Prerequisites
- .NET SDK installed
- Visual Studio, VS Code, or Rider
- Git installed
- Terminal access (PowerShell recommended)
- Internet connectivity

## Technology Used
- .NET SDK and CLI
- ASP.NET Core Web API template
- C# class library projects
- xUnit test project template
- Git

## Business Use Case / Scenario
You are onboarding a new team to an Enterprise Order Fulfillment Platform. Before implementing features, the team must create a maintainable solution structure that separates API, application logic, domain rules, infrastructure concerns, and tests.

## Target Folder Structure

```text
OrderManagement
|
|-- src
|   |-- OrderManagement.Api
|   |-- OrderManagement.Application
|   |-- OrderManagement.Domain
|   |-- OrderManagement.Infrastructure
|
|-- tests
|   |-- OrderManagement.Tests
```

## Setup Project

### Step 1 - Create working folder

```bash
mkdir claude-dotnet-day1
cd claude-dotnet-day1
```

### Step 2 - Create solution

```bash
dotnet new sln -n OrderManagement
```

### Step 3 - Create project folders

```bash
mkdir src
mkdir tests
```

### Step 4 - Create projects

Create API project:

```bash
dotnet new webapi -o src/OrderManagement.Api
```

Create Application project:

```bash
dotnet new classlib -o src/OrderManagement.Application
```

Create Domain project:

```bash
dotnet new classlib -o src/OrderManagement.Domain
```

Create Infrastructure project:

```bash
dotnet new classlib -o src/OrderManagement.Infrastructure
```

Create test project:

```bash
dotnet new xunit -o tests/OrderManagement.Tests
```

### Step 5 - Add projects to solution

```bash
dotnet sln add src/OrderManagement.Api
dotnet sln add src/OrderManagement.Application
dotnet sln add src/OrderManagement.Domain
dotnet sln add src/OrderManagement.Infrastructure
dotnet sln add tests/OrderManagement.Tests
```

### Step 6 - Configure project references

Application depends on Domain:

```bash
dotnet add src/OrderManagement.Application reference src/OrderManagement.Domain
```

Infrastructure depends on Application and Domain:

```bash
dotnet add src/OrderManagement.Infrastructure reference src/OrderManagement.Application
dotnet add src/OrderManagement.Infrastructure reference src/OrderManagement.Domain
```

API depends on Application and Infrastructure:

```bash
dotnet add src/OrderManagement.Api reference src/OrderManagement.Application
dotnet add src/OrderManagement.Api reference src/OrderManagement.Infrastructure
```

Tests depend on Application and Domain:

```bash
dotnet add tests/OrderManagement.Tests reference src/OrderManagement.Application
dotnet add tests/OrderManagement.Tests reference src/OrderManagement.Domain
```

### Step 7 - Build solution

```bash
dotnet build
```

### Step 8 - Initialize Git and baseline commit

```bash
git init
dotnet new gitignore
git add .
git commit -m "Initial Order Management solution"
```

## Expected Output
- All projects created and added to solution
- Project references configured correctly
- Build succeeds with no errors
- Git repository initialized with baseline commit

Expected build message:

```text
Build succeeded.
```

## Conclusion
You now have a production-style .NET solution skeleton ready for AI-assisted analysis, design, implementation, and testing in the next labs.