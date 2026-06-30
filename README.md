# Grupp 3 TDD Budget Tracker

![GRUPP3](https://img.shields.io/badge/group-3-blue)
![TDD Budget Tracker](https://img.shields.io/badge/TDD-Budget%20Tracker-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)
[![.NET Build & Test](https://img.shields.io/badge/.NET%20Build%20%26%20Test-private-green)](https://github.com/Stephen-Uche/grupp3-tdd-Budget-Tracker-1/actions/workflows/dotnet-desktop.yml)

## Profile

**Project:** Budget Tracker-2  
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
├── BudgetTracker.sln
├── src/
│   ├── BudgetTracker.Api/
│   │   ├── Controllers/
│   │   └── Program.cs
│   ├── BudgetTracker.Core/
│   │   ├── Clients/
│   │   ├── Data/
│   │   ├── Domain/
│   │   ├── Dtos/
│   │   ├── Migrations/
│   │   ├── Repositories/
│   │   └── Services/
│   └── BudgetTracker.Web/
│       ├── Controllers/
│       ├── Models/
│       ├── Views/
│       ├── wwwroot/
│       └── Program.cs
└── tests/
    └── BudgetTracker.Test/
        ├── Integration/
        └── Unit/
```

---

## Projects

- `src/BudgetTracker.Api` - REST API endpoints for accounts, categories, transactions, budgets, reports, and dashboard data.
- `src/BudgetTracker.Core` - Domain models, DTOs, repositories, services, EF Core DbContext, migrations, and clients.
- `src/BudgetTracker.Web` - MVC web interface.
- `tests/BudgetTracker.Test` - Unit and integration tests.

---

## Requirements

- .NET 10 SDK
- SQLite

---

## Configuration

The default SQLite connection string is configured in:

```text
src/BudgetTracker.Api/appsettings.json
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
dotnet run --project src/BudgetTracker.Web/BudgetTracker.Web.csproj
```

Run the REST API:

```bash
dotnet run --project src/BudgetTracker.Api/BudgetTracker.Api.csproj
```

---

## Database Migrations

Migrations live in `BudgetTracker.Core`. From the repository root:

```bash
dotnet ef migrations add <Name> -p src/BudgetTracker.Core -s src/BudgetTracker.Api
dotnet ef database update -p src/BudgetTracker.Core -s src/BudgetTracker.Api
```

In development, the app applies migrations and seeds default data at startup.

---

## Tests

From the repository root:

```bash
dotnet test tests/BudgetTracker.Test/BudgetTracker.Test.csproj
```

Run the full solution:

```bash
dotnet test BudgetTracker.sln
```

Run tests with coverage:

```bash
dotnet test tests/BudgetTracker.Test/BudgetTracker.Test.csproj --collect:"XPlat Code Coverage"
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
