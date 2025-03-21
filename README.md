# Assignment #3 – Actionable Items  
**Scenario:** 
The client, an AI developer, uses web scraping to collect training data but faces some challenges:

1. Separating questions from answers to prevent AI from memorizing responses. 

2. Ensuring balanced datasets to improve AI fairness and accuracy.

---

### Requirement 1:

**User Story:**
_As an AI developer, I want training questions to be categorized separately from answers so that AI models can be tested without being biased by pre-exposed answers._

---

### Assumptions & Validation
- The current dataset does not separate questions from answers.
  - **Method 1:** Review the dataset to confirm that questions and answers are stored together.
- Developers need access to questions only to prevent AI from memorizing answers. 
  - **Method 2:** Ensure an API endpoint exists that retrieves only questions without exposing answers.
- A relational database will help structure and retrieve data efficiently. 
  - **Method 3:** Design a relational schema and test retrieval efficiency with sample queries.
- A manual tagging system is necessary to categorize questions accurately. 
  - **Method 4:** Run a comparative test between automated and manual tagging to ensure manual tagging improves categorization accuracy.

---

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

---

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
### Requirement 2:
**User Story:**
_As an AI developer, I want to ensure that my training data is unbiased so that the AI model can make fair and accurate predictions._

---

### Assumptions & Validation

- Bias exists due to overrepresentation or underrepresentation of certain data.
  - **Method 1:** Perform an initial dataset analysis to identify imbalances in representation.

- Developers need an automated bias detection system to identify and correct imbalances.
  - **Method 2:** Implement a bias detection algorithm and compare results with human expert reviews.

- Statistical analysis is the best way to quantify bias.
  - **Method 3:** Use fairness metrics such as demographic parity and disparate impact analysis to measure bias.

---

### Actionable Items

1. **Implement an automated bias detection algorithm**
   - Identify key bias metrics relevant to the dataset
   - Develop a script to scan and flag imbalances in training data
   - Validate the algorithm's effectiveness by comparing flagged bias cases with human reviews

2. **Develop a bias visualization dashboard**
   - Design a dashboard that displays bias metrics in an interpretable format
   - Implement interactive charts and graphs to show bias trends
   - Ensure real-time data updates for continuous monitoring

3. **Create a bias report generator**
   - Develop a reporting system that summarizes bias detection results
   - Include key fairness metrics and possible corrective measures
   - Automate the report generation for periodic bias assessment

---

### Follow-Up Questions

- What types of biases are most likely present in the dataset?
- How will data imbalance be measured?
- What machine learning techniques will be used for bias detection?
- How will flagged bias cases be reviewed and validated?
- How frequently should bias reports be generated?
- Should there be an option to compare bias trends over time to monitor improvements?
- How will the system accommodate future expansions, such as additional fairness metrics or new bias types?

---
