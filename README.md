# Credit Score Analysis Tool - Swedbank (Sweden)

## Description
The Credit Score Analysis Tool is an automated platform designed to evaluate credit scores in real-time by integrating data from multiple sources. It provides predictive analytics to enhance decision-making speed. The system leverages a microservices architecture to ensure scalability and efficiency.

## Key Features
1. Real-time Credit Scoring: Uses Kafka for fast and efficient decision-making.
2. Secure User Authentication: OAuth integration for secure login and user management.
3. Optimized Performance: Redis caching for improved application performance and reduced database load.
4. Scalable Microservices Architecture: Designed for easy deployment and future-proof scalability.

## Responsibilities
1.Developed a real-time credit scoring system using Kafka for faster decision-making.
2.Built and integrated REST APIs and business features for seamless functionality.
3.Implemented OAuth for secure user authentication.
4.Optimized performance with Redis caching, reducing database load.
5.Designed a microservices architecture for easy deployment and maintenance as a personal learning project.

## Technologies Used
1.Kafka: For real-time data streaming and decision-making.
2.OAuth: For secure user authentication.
3.Redis: For data caching and performance optimization.
4.Microservices: For scalable and efficient system design.


## Data Layer / Schemas:

### Users Table

a. user_id (Primary Key)

b. username

c. password_hash

d. email

e. role

f. created_at

g. updated_at

h. last_login

i. status (e.g., active, inactive)

### Credit Scores Table

a. credit_score_id (Primary Key)

b. user_id (Foreign Key)

c. score

d. date

e. score_type (e.g., FICO, VantageScore)

f. score_history (JSON or array to track historical scores)

g. algorithm_used (details about the scoring algorithm)

### Financial Records Table

a. record_id (Primary Key)

b. user_id (Foreign Key)

c. transaction_date

d. amount

e. transaction_type (e.g., credit, debit)

f. transaction_description

g. category (e.g., utilities, groceries, entertainment)

### Audit Logs Table
a. log_id (Primary Key)

b. user_action

c. timestamp

d. user_id (Foreign Key)

e. details (description of the action take

### Reports Table
a. report_id (Primary Key)

b. user_id (Foreign Key)

c. credit_score_id (Foreign Key)

d. generated_date

e. report_data (possibly stored as JSON or XML)

f. report_type (e.g., standard, detailed)

## REST APIs:

### Data Collection Service
1. GET /data/{userId} - Retrieves all financial data for a specific user.
2. GET /data/{userId}/transactions - Retrieves transaction history for a user.
3. POST /data - Submits new financial data.
4. PUT /data/{userId} - Updates existing financial data for a user.
5. DELETE /data/{userId} - Removes financial data for a user.
6. GET /data/{userId}/loans - Fetches loan data for a user.
7. POST /data/batch - Submits financial data for multiple users.
8. GET /data/stats - Provides statistics about collected data.

### Credit Scoring Service
1. GET /score/{userId} - Fetches the credit score for a user.
2. POST /score/calculate - Calculates the credit score based on provided data.
3. PUT /score/{userId} - Updates the credit score for a user.
4. DELETE /score/{userId} - Deletes the credit score data for a user.
5. GET /score/history/{userId} - Retrieves the score history of a user.
6. POST /score/batch - Calculates scores for multiple users.
7. GET /score/average - Provides the average score across all users.
8. PUT /score/refresh - Refreshes and recalculates scores based on latest data.
   
### User Management Service
1. GET /users/{userId} - Retrieves user details.
2. POST /users - Registers a new user.
3. PUT /users/{userId} - Updates user details.
4. DELETE /users/{userId} - Deletes a user.
5. GET /users/all - Retrieves all users.
6. POST /users/authenticate - Authenticates user login.
7. PUT /users/{userId}/password - Updates a user's password.
8. GET /users/{userId}/status - Checks the status of a user's account.

### Report Service
1. GET /reports/{userId} - Fetches all credit reports for a user.
2. POST /reports/generate - Generates a new credit report.
3. PUT /reports/{reportId} - Updates a specific report.
4. DELETE /reports/{reportId} - Deletes a specific report.
5. GET /reports/{reportId} - Retrieves a specific report.
6. POST /reports/batch - Generates reports for multiple users.
7. GET /reports/stats - Provides statistics on generated reports.
8. PUT /reports/{reportId}/send - Sends a report to a specified recipient.


## How to Run
1. Clone the repository.

2.Set up Kafka and Redis services.

3.Configure OAuth for authentication.

4.Run the microservices application.
