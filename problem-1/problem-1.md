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

A JSON file has been prepared containing 10 examples of resume entries, focusing only on the "basics" section of the JSON Resume schema.

This JSON file can be used for the Elasticsearch indexing practice. Participants will load the data from this file into Elasticsearch, learning how to index documents and start working with structured data.

```json
[
    {
        "name": "Alice Johnson",
        "title": "Software Engineer",
        "email": "alice.johnson@example.com",
        "phone": "555-0110",
        "summary": "Experienced software engineer",
        "languages": ["Portuguese", "French"],
        "years_of_experience": 10,
        "available_for_work": false,
        "birthdate": "1992-10-17"
    },
    {
        "name": "Bob Smith",
        "title": "Software Engineer",
        "email": "bob.smith@example.com",
        "phone": "555-0111",
        "summary": "Skilled data analyst",
        "languages": ["English", "Spanish"],
        "years_of_experience": 7,
        "available_for_work": true,
        "birthdate": "1991-03-03"
    },
    {
        "name": "Candidato 3",
        "title": "Project Manager",
        "email": "candidato3@example.com",
        "phone": "555-0112",
        "summary": "Efficient project manager",
        "languages": ["German"],
        "years_of_experience": 3,
        "available_for_work": false,
        "birthdate": "1987-07-21"
    },
    {
        "name": "Jack Martinez",
        "title": "Data Analyst",
        "email": "jack.martinez@example.com",
        "phone": "555-0113",
        "summary": "Data analyst with deep understanding best software practices for data manipulation in engineering domain",
        "languages": ["Portuguese"],
        "years_of_experience": 5,
        "available_for_work": true,
        "birthdate": "1995-11-11"
    },
    {
        "name": "Isabel Thomas",
        "title": "UX Designer",
        "email": "isabel.thomas@example.com",
        "phone": "555-0114",
        "summary": "Creative UX designer with a user-centric approach",
        "languages": ["English", "French"],
        "years_of_experience": 8,
        "available_for_work": true,
        "birthdate": "1990-04-05"
    },
    {
        "name": "Henry Wilson",
        "title": "Marketing Specialist",
        "email": "henry.wilson@example.com",
        "phone": "555-0115",
        "summary": "Innovative marketing specialist",
        "languages": ["Spanish", "English"],
        "years_of_experience": 4,
        "available_for_work": true,
        "birthdate": "1988-08-18"
    },
    {
        "name": "Grace Lee",
        "title": "Network Administrator",
        "email": "grace.lee@example.com",
        "phone": "555-0116",
        "summary": "Skilled network administrator",
        "languages": ["French"],
        "years_of_experience": 6,
        "available_for_work": true,
        "birthdate": "1985-02-27"
    },
    {
        "name": "Frank Miller",
        "title": "HR Manager",
        "email": "frank.miller@example.com",
        "phone": "555-0117",
        "summary": "Human resources manager with extensive experience",
        "languages": ["German", "Portuguese"],
        "years_of_experience": 9,
        "available_for_work": true,
        "birthdate": "1983-05-14"
    },
    {
        "name": "Eve Davis",
        "title": "Business Analyst",
        "email": "eve.davis@example.com",
        "phone": "555-0118",
        "summary": "Detail-oriented business analyst",
        "languages": ["English"],
        "years_of_experience": 2,
        "available_for_work": true,
        "birthdate": "1992-12-29"
    },
    {
        "name": "David Brown",
        "title": "Graphic Designer",
        "email": "david.brown@example.com",
        "phone": "555-0119",
        "summary": "Graphic designer known for creative solutions",
        "languages": ["Spanish", "French"],
        "years_of_experience": 7,
        "available_for_work": true,
        "birthdate": "1989-09-09"
    }
]
```