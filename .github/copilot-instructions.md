# Project: [YourAppName] Migration

## What this project is
A legacy .NET monolith being migrated to React (frontend) + Java Spring Boot 
(services) + Databricks (data layer). Migration is in progress — do not assume 
the codebase is consistent. Some modules are already migrated, others are not.

## Source stack
- .NET Framework [version] monolith
- SQL Server with 3 schemas: [Schema1], [Schema2], [Schema3]
- Heavy use of stored procedures for business logic
- [Any ORM? Dapper/EF? Note it here]

## Target stack
- React + TypeScript (frontend)
- Java 17 + Spring Boot 3 (services)
- Databricks (final data layer) — NOT YET LIVE
- DuckDB (interim stand-in for Databricks during migration)

## Current migration state
- Already migrated: [list screens/modules done]
- In progress: [current focus]
- Not started: everything else

## Database critical context
- Schema1 ([name]): owns [describe domain e.g. customer, orders]
- Schema2 ([name]): owns [describe domain]
- Schema3 ([name]): owns [describe domain]
- Cross-schema joins exist — never assume a table belongs to one service
- DuckDB is temporary — do not build Databricks-specific assumptions into 
  Java services yet. Use repository interfaces to abstract the data layer.

## Stored procedures
- Business logic lives heavily in stored procedures, not the .NET layer
- When analysing any feature, always check if a stored proc is doing 
  validation, calculation, or audit logic before assuming the controller owns it
- Stored proc naming convention: [e.g. usp_SchemaName_ActionName]

## What NOT to do
- Do not suggest Entity Framework patterns — we are not using EF in Java layer
- Do not collapse schemas into one — each schema will become its own service domain
- Do not generate Databricks-specific SQL yet — use ANSI SQL compatible with DuckDB
- Do not assume a screen maps 1:1 to one service — cross-domain screens exist

## Migration documentation standard
Every feature must produce a Feature Documentation Card before any code is written.
See `.github/prompts/scan-feature.prompt.md` for the template.

## Key contacts / ownership
[Optional: who owns which domain, useful if team is involved]
