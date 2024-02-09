## Objective of the Week

Deepen your understanding of data modeling in Elasticsearch, focusing on complex data structures such as nested objects and parent-child relationships.

## Proposed Problem

Context: The recruitment company needs more detailed resumes, including information about professional experiences, education, skills, and certifications, while maintaining the logical relationship between these data points and using the most efficient modeling for storage and retrieval.

### Challenge of the Week

Implement a data model in Elasticsearch that supports more complex data structures. Index sample data representing detailed resumes and perform queries to extract relevant insights.

Conduct queries that can answer the following questions:

- Which candidates have experience in a specific company?
- List candidates by the number of certifications.
- Which candidates have work experiences that started and ended within the range of 2014 to 2019?
- Who has a certification issued by "Shields LLC"?
- Who worked as a "Software Engineer" at the "Schaden Group"?
- Which candidates have more than 3 years of experience as a "Software Engineer"?
- Identify candidates who transitioned from the "Data Analyst" career to "Software Engineer." (order doesn't matter)

### Expected Outcome

- Implementation of a complex data model in Elasticsearch.
- Ability to effectively index and query structured data using nested objects and parent-child relationships.

### Theoretical Content

- Relationships in Elasticsearch: Understanding different types of data relationships (such as one-to-many and many-to-many) and how they are represented in Elasticsearch.

- Nested Objects: Learning about the use of nested fields to model arrays of objects, maintaining independence between elements.

- Parent-Child Relationships: Exploring the concept of parent-child relationships in Elasticsearch, useful for modeling complex relationships between documents.