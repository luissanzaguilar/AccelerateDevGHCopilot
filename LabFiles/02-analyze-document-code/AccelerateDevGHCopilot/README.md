# Library App

## Description

Library App is a .NET 9 console application for managing library patrons and book loans. Users can search for patrons, view their membership and loans, renew memberships, extend loans, and mark books as returned. The app stores authors, books, book items, patrons, and loans in JSON files.

## Project Structure

- `src/`
  - `Library.Console/`
    - `ConsoleApp.cs` - Console interface and application workflow.
    - `Program.cs` - Configuration, dependency injection, and startup.
    - `appSettings.json` - JSON data file paths.
    - `Json/` - Author, book, book item, patron, and loan data.
  - `Library.ApplicationCore/`
    - `Entities/` - Library domain entities.
    - `Enums/` - Status values and enum helpers.
    - `Interfaces/` - Service and repository contracts.
    - `Services/` - Patron and loan operations.
  - `Library.Infrastructure/`
    - `Data/` - JSON-backed repositories and data loading/saving.
- `tests/`
  - `UnitTests/` - xUnit tests for application services.

## Key Classes and Interfaces

- `ConsoleApp` - Runs the interactive console workflow.
- `PatronService` and `LoanService` - Apply membership and loan rules.
- `IPatronRepository` and `ILoanRepository` - Define the data operations used by application services.
- `JsonPatronRepository` and `JsonLoanRepository` - Implement repository operations using JSON data.
- `JsonData` - Loads and saves JSON records and populates related entities, such as a loan's book and patron.

## Usage

Install the .NET 9 SDK, then run these commands from the repository root:

```bash
dotnet run --project src/Library.Console/Library.Console.csproj
```

Follow the console prompts to search for patrons and manage their memberships and loans. To run the unit tests:

```bash
dotnet test tests/UnitTests/UnitTests.csproj
```

## License

This project is licensed under the MIT License. See the repository-level `LICENSE` file for details.