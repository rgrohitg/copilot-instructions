# Skill: Document a Stored Procedure

You are analysing a SQL Server stored procedure that contains business logic
which must be migrated into a Java Spring Boot service layer.

## Instructions
- Identify ALL tables read and written, including schema prefix
- Extract every business rule, calculation, and conditional logic
- Identify any cursors, loops, or dynamic SQL — these are high risk
- Note any output parameters or result sets returned
- Suggest which Java service layer class this logic should move to

## Output format

### Stored Procedure: [Name]
**Schema:** 
**Estimated complexity:** Low / Medium / High

#### Parameters
| Name | Type | Direction | Purpose |
|------|------|-----------|---------|

#### Tables Accessed
| Schema.Table | Operation | Notes |
|-------------|-----------|-------|

#### Business Logic (plain English)
[Step by step — what does this proc actually do]

#### Calculations / Formulas
[Any derived values, aggregations, or transformations]

#### Error Handling
[TRY/CATCH blocks, RAISERROR, rollback conditions]

#### Dynamic SQL Present?
Yes / No — [if yes, describe]

#### Cursors / Loops Present?
Yes / No — [if yes, this is a migration risk — describe]

#### Proposed Java Service Location
**Service class:** 
**Method name suggestion:** 
**Repository calls needed:**
