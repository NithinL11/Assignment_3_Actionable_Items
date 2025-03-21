# Assignment #3 – Actionable Items  
**Scenario:** 
The client, an AI developer, uses web scraping to collect training data but faces some challenges:

1. Separating questions from answers to prevent AI from memorizing responses. 

2. Ensuring balanced datasets to improve AI fairness and accuracy.

---

### Requirement 1:

**User Story:**
_As an AI developer, I want training questions to be categorized separately from answers so that AI models can be tested without being biased by pre-exposed answers._

### Assumptions & Validation
- The current dataset does not separate questions from answers.
  - **Method 1:** Review the dataset to confirm that questions and answers are stored together.
- Developers need access to questions only to prevent AI from memorizing answers. 
  - **Method 2:** Ensure an API endpoint exists that retrieves only questions without exposing answers.
- A relational database will help structure and retrieve data efficiently. 
  - **Method 3:** Design a relational schema and test retrieval efficiency with sample queries.
- A manual tagging system is necessary to categorize questions accurately. 
  - **Method 4:** Run a comparative test between automated and manual tagging to ensure manual tagging improves categorization accuracy.

### Actionable Items
1. **Develop a database schema to store questions and answers separately**
   - Define database tables (`questions`, `answers`, `tags`)
   - Implement foreign key relationships to maintain integrity
   - Test database queries to ensure proper data retrieval

2. **Implement an API to retrieve only questions while restricting answer access**
   - Develop an API endpoint to fetch categorized questions
   - Implement authentication to restrict unauthorized access
   - Conduct security testing to ensure answers remain inaccessible

3. **Develop a manual tagging system to categorize questions**
   - Design an interface (UI or API) for tagging questions
   - Store and manage tagged metadata in the database
   - Validate and refine the system by comparing manual and automated tagging accuracy

### Follow-Up Questions
- Are there existing labels or metadata that indicate a distinction between questions and answers? 
- Are there duplicate entries in the dataset that might affect categorization?
- What authentication and authorization methods will be implemented to restrict access to answers?
- Should the API support filtering or searching by specific categories?
- How will the API handle scalability if multiple developers query the questions simultaneously?
- How will the schema accommodate future expansions, such as additional tags? 
- How will indexing and query optimization techniques be applied to ensure fast retrieval? 
- What database management system will be used for storing questions and answers separately? 

---
