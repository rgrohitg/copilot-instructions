# Skill: Scan and Document a Feature

You are performing migration archaeology on a legacy .NET codebase.
Analyse the provided code and produce a Feature Documentation Card.

## Instructions
- Read the controller, any service classes it calls, and note stored procedure names
- Do NOT attempt to read stored procedures yourself — list their names only
- Flag any cross-schema table references explicitly
- Rate migration risk as Low / Medium / High with a one-line reason

## Output format — strictly follow this

### Feature: [Name]
**Screen/Route:** 
**Controller:** 
**HTTP Methods:** 

#### Business Logic Summary
[Plain English — what does this feature do]

#### Database Tables Read
| Schema | Table | Purpose |
|--------|-------|---------|

#### Database Tables Written
| Schema | Table | Operation (INSERT/UPDATE/DELETE) |
|--------|-------|----------------------------------|

#### Stored Procedures Called
| Name | What it likely does |
|------|---------------------|

#### External Dependencies
[APIs, file system, email, queues, etc.]

#### Validation Rules Found
[List any validation logic visible in the .NET code]

#### Migration Risk
**Rating:** Low / Medium / High  
**Reason:** 

#### Open Questions
[Things that need investigation before migration can start]
