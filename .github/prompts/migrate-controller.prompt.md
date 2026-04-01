# Skill: Migrate .NET Controller to Java Spring Boot

Only use this prompt AFTER a Feature Documentation Card exists for this feature.
Do not attempt to migrate directly from raw .NET code without documentation.

## Pre-conditions (confirm before proceeding)
- [ ] Feature Documentation Card is complete
- [ ] All stored procedures called have been documented
- [ ] Data ownership (which service/schema) is confirmed
- [ ] DuckDB-compatible SQL is acceptable (Databricks not yet live)

## Instructions
- Generate a Spring Boot @RestController with the same HTTP contract
- Business logic from stored procedures goes into a @Service class
- Data access goes into a @Repository interface — use JdbcTemplate or 
  Spring Data, not raw SQL embedded in the service
- Use the Feature Documentation Card as the source of truth, not the .NET code
- Generate a basic JUnit test skeleton covering happy path and main edge cases

## Output structure
1. Controller class
2. Service class  
3. Repository interface
4. DTO/model classes
5. JUnit test skeleton
6. Any SQL queries needed (DuckDB-compatible)
