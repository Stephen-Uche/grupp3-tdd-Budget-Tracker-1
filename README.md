# Grupp 3 TDD Budget Tracker

![GRUPP3](https://img.shields.io/badge/group-3-blue)
![TDD Budget Tracker](https://img.shields.io/badge/TDD-Budget%20Tracker-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)
[![.NET Build & Test](https://img.shields.io/badge/.NET%20Build%20%26%20Test-private-green)](https://github.com/Stephen-Uche/grupp3-tdd-Budget-Tracker-1/actions/workflows/dotnet-desktop.yml)

## Profile

**Project:** Budget Tracker  
**Team:** Grupp 3  
**Focus:** Test-driven development, clean architecture, and practical budget management  
**Goal:** Build a personal budget application with a maintainable Core layer, REST API, MVC web interface, and automated tests.

---

## The Vision

BudgetTracker helps users organize accounts, categories, transactions, budgets, reports, and dashboard insights in one place. The project is built as a learning-focused .NET application where the team practices TDD, separation of concerns, Entity Framework Core, SQLite persistence, MVC views, and API testing.

---

## Milestones

- [x] **Core architecture:** Domain models, DTOs, service layer, repositories, and EF Core DbContext
- [x] **Web application:** MVC pages for dashboard, accounts, categories, transactions, and budgets
- [x] **REST API:** API controllers for accounts, categories, transactions, budgets, reports, and dashboard data
- [x] **Persistence:** SQLite database with EF Core migrations and seed data
- [x] **Testing:** Unit and integration tests with xUnit, FluentAssertions, NSubstitute, and WebApplicationFactory
- [x] **CI:** GitHub Actions workflow for build and test

---

## Stack

- .NET 10
- ASP.NET Core MVC
- Entity Framework Core
- SQLite
- xUnit
- FluentAssertions
- NSubstitute
- Coverlet collector
- GitHub Actions

---

## Project Structure

```text
BudgetTracker/
├── BudgetTracker.sln
├── BudgetTracker.Core/
│   ├── Clients/
│   ├── Data/
│   ├── Domain/
│   ├── Dtos/
│   ├── Migrations/
│   ├── Repositories/
│   └── Services/
├── BudgetTracker.Web/
│   ├── Controllers/
│   ├── Models/
│   ├── Views/
│   ├── wwwroot/
│   └── Program.cs
└── BudgetTracker.Tests/
    ├── Integration/
    └── Unit/
```

---

## Requirements

- .NET 10 SDK
- SQLite

---

## Configuration

The default SQLite connection string is configured in:

```text
BudgetTracker/BudgetTracker.Web/appsettings.json
```

Optional 1minAI configuration can be set with environment variables:

```bash
export ONEMINAI_API_KEY="your-key"
export ONEMINAI_MODEL="gpt-4o-mini"
```

PowerShell:

```powershell
$env:ONEMINAI_API_KEY="your-key"
$env:ONEMINAI_MODEL="gpt-4o-mini"
```

---

## Run the Application

From the repository root:

```bash
dotnet run --project BudgetTracker/BudgetTracker.Web/BudgetTracker.Web.csproj
```

The MVC web app and API run from the same ASP.NET Core host. API endpoints are exposed under `/api`.

---

## Database Migrations

Migrations live in `BudgetTracker.Core`. From the `BudgetTracker` folder:

```bash
dotnet ef migrations add <Name> -p BudgetTracker.Core -s BudgetTracker.Web
dotnet ef database update -p BudgetTracker.Core -s BudgetTracker.Web
```

In development, the app applies migrations and seeds default data at startup.

---

## Tests

From the repository root:

```bash
dotnet test BudgetTracker/BudgetTracker.Tests/BudgetTracker.Tests.csproj
```

Run the full solution:

```bash
dotnet test BudgetTracker/BudgetTracker.sln
```

Run tests with coverage:

```bash
dotnet test BudgetTracker/BudgetTracker.Tests/BudgetTracker.Tests.csproj --collect:"XPlat Code Coverage"
```

---

## Team Members

- **Rayan Care** - Core
- **Stephan** - API
- **Ahmed** - Web

---

## Notes

Built during the bootcamp as a group TDD project. The repository tracks progress, implementation decisions, and testing practice while shipping a working budget management app.

## License

MIT
