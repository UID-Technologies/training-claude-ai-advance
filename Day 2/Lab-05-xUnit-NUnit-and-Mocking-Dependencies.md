# Lab 05 - xUnit, NUnit, and Mocking Dependencies

## Lab Name
Test Suite Expansion, Framework Comparison, and Dependency Isolation

## Description
This lab builds a robust test suite, compares xUnit and NUnit conventions, and introduces dependency mocking patterns using Moq.

## Prerequisites
- Completion of Labs 00-04
- Working test projects

## Technology Used
- xUnit
- NUnit
- Moq
- C# interfaces and dependency-driven tests

## Business Use Case / Scenario
Modernization changes must be validated through comprehensive automated tests, including scenarios involving external dependencies and failure paths.

## Step-by-Step Details

### Part A - Build xUnit suite

Step 1 - Generate test matrix:

```text
Create a comprehensive unit-test matrix for LoanService.

Include:
- happy paths
- validation
- exact boundaries
- invalid input
- exception scenarios
- business-rule branches

Do not generate code yet.
```

Step 2 - Approve scenarios:
- CreditScore 651 -> Approved
- CreditScore 650 -> Rejected
- Amount 499999 -> Approved
- Amount 500000 -> ManualReview
- Amount 0 -> Reject
- Amount negative -> Reject
- CustomerId 0 -> Reject

Step 3 - Generate Fact tests:

```csharp
[Fact]
public void ProcessLoan_ShouldReject_WhenCustomerIdIsZero()
{
    var service = new LoanService();

    Assert.Throws<Exception>(
        () => service.ProcessLoan(0, 100000, 700));
}
```

Step 4 - Generate Theory tests:

```csharp
[Theory]
[InlineData(651, "Approved")]
[InlineData(650, "Rejected")]
[InlineData(600, "Rejected")]
public void ProcessLoan_ShouldReturnExpectedStatus(
    int creditScore,
    string expected)
{
    // test implementation
}
```

Step 5 - Run tests:

```bash
dotnet test
```

### Part B - Compare NUnit

Step 1 - Create NUnit test project:

```bash
dotnet new nunit -o tests/LegacyLoan.NUnitTests
dotnet sln add tests/LegacyLoan.NUnitTests
dotnet add tests/LegacyLoan.NUnitTests reference src/LegacyLoan.Services
dotnet add tests/LegacyLoan.NUnitTests reference src/LegacyLoan.Domain
```

Step 2 - Convert attributes:
- xUnit [Fact] -> NUnit [Test]
- xUnit [Theory] + [InlineData] -> NUnit [TestCase]

Step 3 - Add setup style:

```csharp
private LoanService _service = null!;

[SetUp]
public void Setup()
{
    _service = new LoanService();
}
```

Step 4 - Discuss framework differences:
- xUnit prefers constructor/fixture style
- NUnit emphasizes SetUp and TearDown style

### Part C - Mock dependencies with Moq

Step 1 - Define service dependency interfaces:
- ICustomerRepository
- ICreditScoreService
- INotificationService

Step 2 - Add Moq:

```bash
dotnet add tests/LegacyLoan.Tests package Moq
```

Step 3 - Mock success behavior:

```csharp
var customerRepository = new Mock<ICustomerRepository>();
customerRepository
    .Setup(x => x.ExistsAsync(
        It.IsAny<int>(),
        It.IsAny<CancellationToken>()))
    .ReturnsAsync(true);
```

```csharp
var creditScore = new Mock<ICreditScoreService>();
creditScore
    .Setup(x => x.GetScoreAsync(
        It.IsAny<int>(),
        It.IsAny<CancellationToken>()))
    .ReturnsAsync(720);
```

Step 4 - Mock failure behavior:

```csharp
creditScore
    .Setup(x => x.GetScoreAsync(
        It.IsAny<int>(),
        It.IsAny<CancellationToken>()))
    .ThrowsAsync(new TimeoutException());
```

Step 5 - Verify required interaction:

```csharp
notificationMock.Verify(
    x => x.SendDecisionAsync(
        It.IsAny<LoanApplication>(),
        It.IsAny<CancellationToken>()),
    Times.Once);
```

## Expected Output
- Balanced xUnit suite with boundaries and negative scenarios
- Side-by-side NUnit comparison implemented
- Dependency interactions isolated and testable with Moq
- Failure paths for external dependencies covered

## Conclusion
Strong modernization depends on test depth, framework literacy, and realistic dependency isolation strategy.