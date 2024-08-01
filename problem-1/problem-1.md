## Objective of the Week

Understand what Elasticsearch is, its basic components, and perform the first indexing and basic document queries.

## Proposed Problem

Context: A recruitment company wants to efficiently organize and access basic information about candidates who have participated in the company's selection processes. To achieve this, you should use Elasticsearch.

Task: The initial goal is to create an index in Elasticsearch that stores resumes with candidate data. For now, the resumes are incomplete and include only fundamental information such as name, title, email, phone, a profile summary, languages ​​the candidate is proficient in, years of experience, whether the candidate is available for immediate work, and the date of birth.

### Challenge of the Week

- Set up an Elasticsearch environment.
- Create an index based on the "basics" section of the JSON Resume schema.
- Index sample documents containing basic information about fictional candidates.
- Ensure that the index allows efficient searching of basic candidate information.
- Perform basic queries to retrieve and analyze resume information to understand how different types of fields impact queries and analyses in Elasticsearch. Queries to be performed
  - Document with ID 1 in Elasticsearch
  - People with more than 5 years of experience available for immediate work
  - People who have the exact phrase "software engineer" in the summary.
  - Find candidates whose title is "Data Analyst."
  - Filter candidates with 5 to 10 years of experience.
  - Find candidates who speak English.
  - Find candidates who speak English or Spanish.
  - Find candidates who speak Spanish and French (simultaneously).

### Expected Outcome

- Elasticsearch installed and configured locally using Docker.
- An Elasticsearch index configured to store the "basics" section of the JSON Resume schema.
- Fictional documents successfully indexed, using the most efficient field types for the proposed queries, and the ability to perform basic searches on this index.

### Theoretical Content

Introduction to Elasticsearch:

- What is Elasticsearch and common use cases.
- Architecture and basic principles of Elasticsearch.
- Differences and advantages over traditional database systems.
- Basic Components of Elasticsearch:
  - Understanding clusters, nodes, shards, and replicas
  - Understanding indices and documents in the context of Elasticsearch.
- Basic of Types in Elasticsearch
  - Understanding different types of fields.
  - Exploration of strategies to choose the appropriate field type for different types of data.
  - Mapping of fields and its importance in data retrieval and analysis.
- Basic Queries of Indexed Data:
- Querying data with Search Lite and Query DSL.

### Assets

A bulk insert request file has been prepared containing 10 examples of resume entries, focusing only on the "basics" section of the JSON resume schema.

This bulk insert request can be used for the Elasticsearch indexing practice. Participants will load the data from this file into Elasticsearch, learning how to index documents and start working with structured data.

