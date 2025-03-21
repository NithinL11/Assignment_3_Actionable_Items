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

### Requirement 3:

**User Story:**
_As an AI developer, I want the training data to be analyzed for balance across different categories so that the AI model does not favor certain inputs over others._

---

### Assumptions & Validation

- AI model performance declines when trained on skewed datasets.
  - **Method 1:** Conduct performance benchmarking to compare model accuracy on balanced vs. imbalanced datasets.

- A dataset balance-checking tool is required
  - **Method 2:** Develop an algorithm that quantifies category distribution and flags imbalances.

- Developers need a visual tool to assess and correct dataset balance
  - **Method 3:** Implement a visualization dashboard that highlights imbalanced categories and suggests corrective actions.

---

### Actionable Items

1. **Develop a data distribution analysis tool**
   - Identify key dataset categories and measure their distribution
   - Implement statistical methods to detect significant imbalances
   - Provide data summaries and visual insights to help assess dataset balance

2. **Create a dataset balance visualization dashboard**
   - Design a user-friendly interface to visually inspect dataset balance
   - Implement graphs, pie charts, and histograms to clearly show how data is distributed across categories
   - Ensure real-time updates to reflect dataset changes dynamically

3. **Implement an imbalance detection & alert system**
   - Develop an automated alert mechanism when dataset imbalance thresholds are exceeded
   - Provide actionable recommendations on how to rebalance the dataset
   - Enable exportable reports summarizing detected imbalances, helping developers make informed decisions

---

### Follow-Up Questions

- How frequently should dataset balance be assessed?
- What statistical tests should be used to measure dataset balance?
- Should the tool support multiple datasets or focus on a single dataset at a time?
- What criteria should trigger an imbalance alert?
- Should the alert system support different severity levels?

---

### Requirement 4: 

**User Story:** 
_As an AI developer, I want to ensure that the training data collected through web scraping is clean and consistent so that AI models can be trained without errors caused by duplicate data._

---

###  Assumptions & Validation

- Web scraping often results in duplicate, missing, or incorrect data.
  - **Method 1:** Perform an initial dataset scan to detect duplicates and missing values.

- Inconsistent data can negatively impact AI model accuracy.
  - **Method 2:** Compare model performance on cleaned vs. uncleaned datasets.

- A data-cleaning and validation process will improve the reliability of the training dataset.
  - **Method 3:** Implement automated scripts to clean and validate data before AI model training.

---

###  Actionable Items

1. **Implement a duplicate detection and removal system**
   - Identify and remove duplicate entries from the dataset
   - Use hash-based or similarity-based techniques to detect near-duplicates
   - Validate dataset integrity after deduplication

2. **Develop automated validation scripts to check for inconsistencies**
   - Implement scripts to detect missing or incorrect data
   - Apply rule-based validation checks
   - Ensure logging for any data inconsistencies found

3. **Create logging and reporting tools for incorrect data entries**
   - Develop a logging mechanism to track data quality issues
   - Generate periodic reports on dataset health and corrections applied
   - Provide developers with actionable insights for manual review and correction

---

###  Follow-Up Questions

- What criteria will define a duplicate entry in the dataset?
- How frequently should data quality reports be generated and reviewed?
- What information should be included in the reports to help developers take corrective action?
- Should the validation process run automatically after each scraping session or on a scheduled basis?

---

### Requirement 5:

**User Story:** 
_As an AI developer, I want to track the source and history of training data so that I can verify its reliability and ensure compliance with ethical AI standards._

---

###  Assumptions & Validation

- Developers need to know where data is scraped from to avoid legal or ethical issues.
  - **Method 1:** Store metadata for each data entry including source URL and timestamp.

- Tracking dataset modifications is essential for debugging AI model performance.
  - **Method 2:** Implement a logging system to track all changes made to the dataset over time.

- A data provenance system improves transparency and trustworthiness.
  - **Method 3:** Create a user-accessible dashboard that displays the full history and origin of data entries.

---

###  Actionable Items

1. **Implement metadata tracking for each dataset entry**
   - Store details like source URL, scrape timestamp, and content type
   - Link metadata to each data record for traceability

2. **Develop an audit log to track data modifications**
   - Record each change to data entries including the time, user/system, and nature of the change
   - Ensure logs are immutable and securely stored

3. **Create a user-accessible dashboard to review data provenance**
   - Display original source and change history for each dataset entry
   - Include filtering options (e.g., by date, category, user)
   - Ensure the dashboard is readable and secure for developer use

---

###  Follow-Up Questions

- What system or role will be responsible for reviewing and maintaining the audit logs?
- What filtering or search capabilities should the dashboard provide to efficiently review provenance data?
- Should access to provenance data be restricted based on user roles or permissions?

---

GitLink :- https://github.com/NithinL11/Assignment_3_Actionable_Items
