
# 🛍️ Doqon — Modular Retail POS System

**Doqon** is a modern, clean-architecture-based Point-of-Sale system for retail stores.  
Built with CQRS, MediatR, and layered architecture, it supports sales, inventory management, customer debts, and multi-currency operations.  
Initially developed for WPF, designed for future transition to .NET MAUI and web interfaces.

---

## 📸 Preview (coming soon...)

> UI screenshots will be placed here once the MVP is deployed.

---

## ⚙️ Technologies Used

- **.NET 9** (.NET MAUI + WPF + ASP.NET Core Web API)
- **Clean Architecture** (Domain, Application, Infrastructure, Presentation)
- **CQRS + MediatR** (Command and Query responsibility segregation)
- **FluentValidation** (Input validation)
- **AutoMapper** (DTO to Entity mapping)
- **EF Core + PostgreSQL** (Database and persistence)
- **Refit** (Typed HTTP clients)
- **Serilog** (Structured logging)
- **JWT Authentication**
- **XUnit + Moq** (Testing)

---

## 🏗️ Project Structure

```bash
/src
  ├── Core
  │   ├── Doqon.Domain           # Entities, ValueObjects, Aggregates, Events
  │   ├── Doqon.Application      # CQRS handlers, DTOs, Interfaces
  │   └── Doqon.Contracts        # API request/response models for clients
  │
  ├── Shared
  │   └── Doqon.Common           # Result<T>, Exceptions, Utilities
  │
  ├── Backend
  │   ├── Doqon.Infrastructure  # EF Core + external services
  │   └── Doqon.Api             # ASP.NET Core Web API
  │
  ├── Client
  │   ├── Doqon.ApiClient       # Refit interfaces for MAUI
  │   └── Doqon.Maui            # Cross-platform frontend (in progress)
  │
  └── Tests                     # Full test coverage per layer
```
---

## 🚀 Getting Started
### 1. Clone the repo
```bash
git clone https://github.com/yourusername/doqon.git
cd doqon
```

### 2. Setup database (PostgreSQL)
- Create a DB: `doqon_db`
- Set connection string in `appsettings.Development.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Database=doqon_db;Username=postgres;Password=yourpassword"
  }
}
```

### 3. Run EF Core migrations
```bash
cd src/Backend/Doqon.Infrastructure
dotnet ef database update
```

### 4. Run the API
```bash
cd ../../Doqon.Api
dotnet run
```
### 5. (Optional) Run the WPF or MAUI client
> Initial version is WPF based. MAUI version coming soon.
---

## 🧪 Running Tests
```bash
dotnet test
```
Test projects are placed under `/Tests` with coverage across all layers.

---

## 📈 Roadmap
- ✅ Sales, Inventory, Debts module
- ✅ JWT Auth & Roles
- 🔄 Currency Exchange module
- 🖥️ WPF client (initial version)
- 📱 MAUI mobile/desktop client (in progress)
- 🌐 BlazorAdmin dashboard (future)
- 📤 Telegram bot support for inventory alerts (future)
- 📦 Publish Doqon.Common & Contracts as NuGet (future)
---

## 🧠 Credits
Inspired by principles of:

- Robert C. Martin — Clean Architecture
- Jimmy Bogard — Vertical Slice Architecture
- Microsoft .NET Architecture Guides
---

## 📄 License
MIT License © 2025 — [Doqon Team](https://github.com/muqimjon/Doqon?tab=MIT-1-ov-file)
