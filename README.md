# grupp3-tdd-Budget-Tracker

![GRUPP3](https://img.shields.io/badge/group-3-blue)
![TDD Budget Tracker](https://img.shields.io/badge/TDD-Budget%20Tracker-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-green)
![.NET Build & Test](https://github.com/Campus-Molndal-CLO25/grupp3-tdd-Budget-Tracker/actions/workflows/dotnet-desktop.yml/badge.svg)](https://github.com/Campus-Molndal-CLO25/grupp3-tdd-Budget-Tracker/actions/workflows/dotnet-desktop.yml)

## Projektbeskrivning
BudgetTracker är en personlig budgetapplikation byggd i .NET med fokus på **TDD**, tydlig arkitektur och separation av ansvar.  
Projektet består av ett Core-lager, ett REST-API och ett MVC-baserat webbgränssnitt.

## Projects

- `BudgetTracker.Core` - Domain, DTOs, repositories, and services.
- `BudgetTracker.Web` - MVC UI plus REST API endpoints for accounts, transactions, categories, budgets, reports, and dashboard.

## Requirements

- .NET 10 SDK
- SQLite

## Configuration

Set 1minAI configuration via environment variables (optional):

```bash
Linux
export ONEMINAI_API_KEY="your-key"
export ONEMINAI_MODEL="gpt-4o-mini"

Window 
$env:ONEMINAI_API_KEY="din-nyckel-här"
$env:ONEMINAI_MODEL="gpt-4o-mini"

```
`appsettings.json` contains the default SQLite connection string.

## Run the Web UI and API

```bash
dotnet run --project BudgetTracker.Web
```

The API exposes endpoints under `/api` from the same Web host.

## Migrations

Migrations live in `BudgetTracker.Core`. To add and apply migrations:

```bash
dotnet ef migrations add <Name> -p BudgetTracker.Core -s BudgetTracker.Web
dotnet ef database update -p BudgetTracker.Core -s BudgetTracker.Web
```

## Tests

```bash
dotnet test BudgetTracker.Tests/BudgetTracker.Tests.csproj
```
## Coverage
Run coverage with the built-in coverlet collector:
```bash
dotnet test BudgetTracker.Tests/BudgetTracker.Tests.csproj --collect:"XPlat Code Coverage" --settings coverlet.runsettings
```

## Teammedlemmar
- **Rayan Care** – Core  
- **Stephan** – API  
- **Ahmed** – Web  

## License
MIT
