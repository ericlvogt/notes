State is the source of a lot of evil reduce it as much as you can. If you add state realize this is technical debt.
## Entities
Entities should have unique identifiers in them
## Repositories
One thing I like about Domain Driven Design is how it splits your state into Entities.

Implement Repositories to access entities. These are generic however if we keep the implementation so simple and make sure the interfaces tell you exactly what happens then this is okay.

Ex.
Job is my entity
JobRepository is my repository
to get a job I call
JobRepository.Single(id)
to get many jobs call
JobRepository.Many()
to get a job including its related runs
JobRepository.SingleIncludingRuns(id);
to get jobs with a filter
JobRepository.Many(country, city)