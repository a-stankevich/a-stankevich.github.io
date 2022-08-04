# Data modification failed on system-versioned table because transaction time was earlier than period start time for affected records

I've put this error message text in header for search engines to better help those facing the similar problem.

Put the story here, remove numbered list items

1. We have a multi-tenant application. Database per tenant. Table like this:
```sql
create table Books (
	Id int not null primary key identity,
	Title nvarchar(max)
	)
```
2. There is also data in that table
```sql
insert Books (Title)
values ('Anna Karenina'), ('The Great Gatsby'), ('Hamlet'), ('Radical Candor')
```
3. All updates in DB schema is done with migrations. Migrations are tied to specific release.
   In case of that table the migration was like that:
```sql
```
4. There are also integration tests, developer environments, QA, beta and production. Generally (for three years so far) this ensures that scripts will apply well on production.


All my googling around the internet 