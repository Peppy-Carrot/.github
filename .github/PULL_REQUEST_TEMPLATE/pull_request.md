[Add a description or link to an issue]

Note: Merge requests without an adequate description or linked issue will not be reviewed.

### General checklist
- [ ] Unit & Integration specs added for feature.
- [ ] Is your code (regression) tested?
- [ ] If you have multiple commits, please combine them into a few logically organized commits by squashing them.
- [ ] if it makes major changes, check if the README needs to be changed.
- [ ] Development/test seeds added/updated (if required).

When making changes to API
- [ ] Made sure that change is supported across all API versions.
- [ ] Added benchmarks related to changes in the API response time.

When adding data migration
- [ ] Added the execution time of the migration(s) to the MR body.

When dealing with PII of users
- [ ] Columns storing PII are secured (using secrets module)
- [ ] If above data is stored in any other table(e.g. request logs) then that is also encrypted or filtered and stored.
-
### Database checklist

When adding migrations:

- [ ] Updated db/schema.rb
- [ ] Added a down method so the migration can be reverted.
- [ ] Added indexes on new columns if necessary (e.g. when migrating data).
- [ ] Added data migration for historical data if necessary.

When adding or modifying queries to improve performance:

- [ ] Included data that shows the performance improvement, preferably in the form of a benchmark.
- [ ] Included the output of EXPLAIN (ANALYZE, BUFFERS) of the relevant queries.
- [ ] Removed related N+1 Queries.
- [ ] Used bulk inserts/updates to improve perfomance.

When adding tables:

- [ ] Added indexes for fields that are used in statements such as WHERE, ORDER BY, GROUP BY, and JOINs.

When removing columns, tables, indexes or other structures:

- [ ] Made sure the application no longer uses (or ignores) these structures


