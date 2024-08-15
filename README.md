# **LinkedIn-like Database Design with Informatica PowerCenter**
### **Relational Database Schema for a LinkedIn-Like Professional Networking Platform Using Informatica PowerCenter**

---

## **Introduction to Informatica PowerCenter**

### **What is Informatica PowerCenter?**
Informatica PowerCenter is a leading data integration tool used for building enterprise data warehouses. It provides powerful ETL (Extract, Transform, Load) capabilities, enabling organizations to extract data from multiple sources, transform it according to business rules, and load it into a target database. PowerCenter supports a wide range of data integration projects, including data warehousing, data migration, and data synchronization.

### **Architecture:**
![image](https://github.com/user-attachments/assets/0b017d4a-9bd8-4a92-a690-cdf4709b8732)
- **Repository Service**: Maintains Informatica metadata and provides access to the same to other services.
- **Integration Service**: Helps in the movement of data from sources to the targets.
- **Reporting Service**: Generates reports.
- **Nodes**: A computing platform to execute the above services.
- **Informatica Designer**: Creates mappings between source and target.
- **Workflow Manager**: Used to create workflows or other tasks and their execution.
- **Workflow Monitor**: Monitors the execution of workflows.
- **Repository Manager**: Manages the objects in the repository.

### **Key Features of Informatica PowerCenter:**
- **Data Integration**: Seamlessly integrates data from various sources.
- **ETL Process**: Provides robust tools for data extraction, transformation, and loading.
- **Data Quality**: Ensures high-quality data through cleansing and validation processes.
- **Scalability**: Handles large volumes of data and complex transformations.
- **Workflow Automation**: Automates the data integration process, reducing manual intervention.

---

## **ETL Process**

### **Extraction**: 
Data is extracted from various sources, including user input forms and external databases.

### **Transformation**: 
Data is transformed using various Informatica PowerCenter transformations to ensure it adheres to the database schema, including applying business rules, data cleansing, and validation.

### **Loading**: 
Transformed data is loaded into the target database tables.

---

## **Informatica Mappings**
Informatica mappings are used to define the data flow from the source to the target. Each mapping represents a specific data integration task.

## **Workflows and Sessions**
Workflows in Informatica PowerCenter define the execution order of tasks, and sessions represent individual tasks within a workflow. They are used to manage the ETL process, ensuring that data is processed in the correct sequence.

## **Why Use Informatica PowerCenter for this Project?**
Informatica PowerCenter is an ideal choice for this project because it:
- Facilitates complex data transformations necessary for managing user profiles, connections, and content.
- Ensures data integrity across multiple entities like users, posts, and groups.
- Optimizes database performance through efficient ETL processes.
- Provides robust tools for managing user connections, education, experience, and more.

---

## **Project Overview**

### **Preamble**
Designing a database for a LinkedIn-like system requires careful consideration of various entities and their relationships. The aim is to create a schema that supports functionalities like user management, connections, posts, comments, likes, shares, and group memberships.

### **Problem Definition**
This project aims to design a relational database schema for a LinkedIn-like system. The database supports the following features:
- **User Management**: Storing user information and their profiles.
- **Connections**: Managing user connections with status indicators (pending, accepted).
- **Education and Experience**: Recording users' educational backgrounds and work experiences.
- **Skills**: Tracking skills users possess.
- **Content Creation**: Enabling users to create posts, comments, likes, and shares.
- **Groups**: Allowing users to create and join groups with different statuses (pending, accepted, blocked).

### **Objectives**
The primary objectives of this project are:
1. Utilize Informatica PowerCenter to extract, transform, and load (ETL) detailed user information and profiles.
2. Support profile customization with summaries, headlines, and industry information using Informatica transformations.
3. Implement primary keys, foreign keys, and unique constraints within Informatica to maintain data integrity.
4. Leverage Informatica's optimization techniques to analyze query patterns and enhance database performance.
5. Use Informatica transformations to provide functionality for viewing and managing user connections.
6. Maintain comprehensive records of user professional experiences, including companies, roles, and durations, through Informatica mappings.
7. Enable Informatica workflows to create mechanisms for liking and sharing posts.
8. Facilitate the creation and management of user connections, including connection status and dates, through Informatica workflows.

---

## **Entity-Relationship (ER) Diagram**
The ER diagram is a visual representation of the database schema that illustrates the relationships between different entities within the system.
![image](https://github.com/user-attachments/assets/d296ebaa-fdd8-4682-886a-0c6974fb5789)

---

## **Key Relationships**
- **One-to-one** relationship between Users and Profiles.
- **One-to-many** relationship between Users and Connections, Education, Experience, Skills, and Posts.
- **One-to-many** relationship between Posts and Comments, Likes, and Shares.
- **One-to-many** relationship between Users and Groups.
- **Many-to-many** relationship between Users and Group Members.

---

## **Data Set Description**
The following tables are included in the database design:
- **Users**: Stores basic information about users such as their name, email, password, and registration date.
- **Profiles**: Contains user-specific information like job title, industry, location, and summary. Linked to the Users table via a foreign key.
- **Connections**: Manages user connections with status indicators (pending, accepted, blocked).
- **Education**: Stores educational background details such as school name, degree, field of study, and dates.
- **Experience**: Records work experiences, including company name, job title, location, and dates.
- **Skills**: Tracks the skills that users possess.
- **Posts**: Contains user-generated content including the post's content and date.
- **Comments**: Stores comments made on posts.
- **Likes**: Tracks likes made on posts.
- **Shares**: Tracks shares made on posts.
- **Groups**: Stores information about groups created by users.
- **Group_members**: Manages the relationship between groups and users, including membership status.
# LinkedIn-Like System ETL Transformations
# Introduction to Transformations

In the ETL (Extract, Transform, Load) process, **transformations** are essential for converting raw data into a structured and usable format. They involve modifying, cleaning, and enriching data to meet the requirements of the target system or application. Transformations ensure that data is accurate, consistent, and suitable for analysis and reporting.

## Types of Transformations

Transformations can be categorized based on their functionality and the type of data processing they perform. Below are some common types of transformations:

### Source Qualifier Transformation
- **Purpose:** Extracts data from source systems and applies basic filtering or data type conversions. It defines how data is read from the source.
- **Example:** Extracting raw data from database tables, CSV files, or other data sources.

### Filter Transformation
- **Purpose:** Filters out unwanted data based on specified conditions or criteria. It determines which rows are included or excluded from further processing.
- **Example:** Filtering records to include only those where the `Salary` is greater than $50,000.

### Expression Transformation
- **Purpose:** Applies calculations, concatenations, and data manipulations using expressions. It allows for the creation of new calculated fields and modifications to existing data.
- **Example:** Calculating the age of employees based on their date of birth or concatenating first and last names.

### Aggregator Transformation
- **Purpose:** Performs aggregate calculations such as sum, average, count, and grouping operations. It summarizes and consolidates data.
- **Example:** Calculating the total sales amount per region or the average salary by department.

### Joiner Transformation
- **Purpose:** Joins data from two or more sources based on a common key. It combines related data from different tables or datasets.
- **Example:** Joining customer data with order data based on the `CustomerID` field.

### Lookup Transformation
- **Purpose:** Performs lookups on a reference table to enrich data with additional information. It retrieves and matches values from a secondary data source.
- **Example:** Looking up the department name from a department reference table using a `DepartmentID`.

### Router Transformation
- **Purpose:** Routes data to different targets or transformations based on specified conditions. It enables conditional data processing.
- **Example:** Routing records to different tables based on the `Region` (e.g., North, South, East, West).

### Sorter Transformation
- **Purpose:** Sorts data based on one or more columns in ascending or descending order. It prepares data for subsequent processing that requires sorted data.
- **Example:** Sorting employee records by `HireDate` to get the most recent hires first.

### Union Transformation
- **Purpose:** Combines data from multiple sources into a single dataset. It merges datasets with the same structure.
- **Example:** Combining sales data from different regions into a single dataset for comprehensive analysis.

### Update Strategy Transformation
- **Purpose:** Determines how to handle data during update operations. It specifies whether data should be inserted, updated, or deleted based on specified conditions.
- **Example:** Updating customer records in the target table based on changes in the source data.

These transformations are vital in ensuring that data is accurately and effectively processed, enabling meaningful analysis and reporting.


## Scenarios

### Users Who Have a Combination of Specific Skills

**Objective:** Identify users proficient in both Java and Python.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `SKILLS` tables.
   - Source Qualifier Transformations:
     - `SQ_USERS`: Extracts USER_ID, EMAIL, PASSWORD, NAME, LOCATION, and JOIN_DATE.
     - `SQ_SKILLS`: Extracts SKILL_ID, USER_ID, and SKILL_NAME.

2. **Filtering:**
   - Apply `Filter` transformations:
     - `java_filter`: Filters rows where `SKILL_NAME` = "Java".
     - `python_filter`: Filters rows where `SKILL_NAME` = "Python".

3. **Joining:**
   - `Joiner` Transformation: Join the filtered `Java` data with `Python` data based on `USER_ID`.

4. **Loading:**
   - Load the relevant data (USER_ID and NAME) into the `TARGET_COMB_SKILLS` table.
     
![image](https://github.com/user-attachments/assets/ca3172b5-3978-4e96-a017-02cde34850f2)

**Output:**
The `TARGET_COMB_SKILLS` table contains users who have both Java and Python skills.
![image](https://github.com/user-attachments/assets/9d893655-ff24-43d7-9870-250a5e826713)

---

### Top Industries by User Count

**Objective:** Identify industries with the highest user count.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `EXPERIENCE` table using `SQ_EXPERIENCE`.

2. **Aggregation:**
   - `Aggregator` Transformation (`AGG`): Group by `COMPANY_NAME` and count the number of `USER_ID`s.

3. **Ranking:**
   - `Rank` Transformation (`R2`): Rank companies based on user count.

4. **Loading:**
   - Load the aggregated and ranked data (COMPANY_NAME and EMPLOYEE_COUNT) into the `TARGET_TOPCOMPANIES` table.
![image](https://github.com/user-attachments/assets/05186365-fd80-4983-bb5e-34fb7bae08e1)

**Output:**
The `TARGET_TOPCOMPANIES` table displays the top companies by user count.
![image](https://github.com/user-attachments/assets/d2cd58d9-4312-49ce-8a3b-9088fe82ceeb)

---

###  Recommend Posts to Users Based on Their Skills

**Objective:** Recommend posts containing skills listed in users' profiles.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `SKILLS` and `POSTS` tables.
   - Use a `Source Qualifier` to join these tables on `USER_ID`.

2. **Filtering:**
   - `Filter` Transformation: Use `IIF(INSTR(POSTS.CONTENT, SKILLS.SKILL_NAME) > 0, TRUE, FALSE)` to ensure only posts containing skills are passed through.

3. **Loading:**
   - Load relevant data (USER_ID, SKILL_NAME, SKILL_ID, CONTENT) into the `POSTS_RES` table.
![image](https://github.com/user-attachments/assets/64f45819-c9b2-4756-a425-3c9f2b93f7f3)

**Output:**
The `POSTS_RES` table contains posts relevant to the skills listed by users.
![image](https://github.com/user-attachments/assets/e95f5ae5-5997-4da7-8d88-9737af38cc0f)

---

###  Users Who Graduated Within a Specific Year Range

**Objective:** Identify users who graduated between 2011 and 2015.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `EDUCATION` tables using `Source Qualifier` to join on `USER_ID`.

2. **Filtering:**
   - `Expression` Transformation: Calculate and filter the graduation year with the condition `end_date_o >= '2011-01-01' AND end_date_o <= '2015-12-31'`.
   - `Filter` Transformation: Apply the condition to include only relevant records.

3. **Loading:**
   - Load filtered data (USER_ID, NAME, SCHOOL_NAME, START_DATE, and END_DATE) into the target table.
![image](https://github.com/user-attachments/assets/940fecf3-f01d-4c6b-81a3-070db62e65d6)

**Output:**
The target table contains users who graduated between 2011 and 2015.
![image](https://github.com/user-attachments/assets/117852e7-e2aa-4f70-96a7-b01f67797d80)

---

###  Users Who Have Experience in Two or More Different Companies

**Objective:** Identify users who have worked in two or more different companies.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `EXPERIENCE` tables using `Source Qualifier` to join on `USER_ID`.

2. **Aggregation:**
   - `Aggregator` Transformation (`AG`): Count distinct `COMPANY_NAME` values for each user.

3. **Filtering:**
   - `Filter` Transformation: Apply a condition to select users with experience in three or more companies (e.g., `company_count >= 2`).

4. **Loading:**
   - Load the filtered data into the target table.
![image](https://github.com/user-attachments/assets/3528b38d-f1fb-423c-854f-48d93b0789aa)

**Output:**
The target table contains users with experience in two or more different companies.
![image](https://github.com/user-attachments/assets/18858567-705a-4296-afc9-fd92a117ce04)

---

###  Users Studied in IIT or NIT

**Objective:** Identify users who have studied in IIT or NIT.

**Transformation Steps:**
1. **Filtering:**
   - `Filter` Transformation: Select users based on their educational institution, specifically IIT or NIT.

2. **Loading:**
   - Load the filtered data into the target table.
![image](https://github.com/user-attachments/assets/c7e21432-4845-49ea-9de2-23ef96a539d0)

**Output:**
The target table contains users who have studied at IIT or NIT.
![image](https://github.com/user-attachments/assets/45f0f698-8d07-4570-afcc-872ee340a612)

---

###  Evaluating Candidates Based on Average Tenure at Companies

**Objective:** Evaluate candidates based on their average tenure at companies.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `EXPERIENCE` tables using `Source Qualifier` to join on `USER_ID`.

2. **Calculation:**
   - `Expression` Transformation: Compute the duration of each work experience using `DATEDIFF` function.

3. **Aggregation:**
   - `Aggregator` Transformation (`AG`): Sum the total experience duration for each user.

4. **Loading:**
   - Load the aggregated data into the target table.
![image](https://github.com/user-attachments/assets/49103c15-ab3b-4a1f-8dc4-0b3b13acf608)

**Output:**
The target table shows candidates' total experience across all companies.
![image](https://github.com/user-attachments/assets/fe11722c-ae32-4df5-a90c-cd1795117e29)

---

###  Find Users Who Have More Than 2 Connections

**Objective:** Identify users with more than 2 connections.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `CONNECTIONS` tables.

2. **Aggregation:**
   - Aggregate connection counts by `USER_ID`.

3. **Filtering:**
   - `Filter` Transformation: Select users with more than 2 connections.

4. **Loading:**
   - Load the filtered data into the `ACTIVE_USERS` table.
![image](https://github.com/user-attachments/assets/1b327fcb-5931-48ea-a47f-61755ab4ef91)

**Output:**
The `ACTIVE_USERS` table contains users with more than 2 connections.
![image](https://github.com/user-attachments/assets/21e93c26-1c08-48d1-86b2-87ec90a495e4)

---

###  Group User Experiences by Specific Locations Using Router Transformation

**Objective:** Group user experiences based on their locations.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `EXPERIENCE` table.

2. **Routing:**
   - `Router` Transformation: Segregate data into groups based on location (Bangalore, Delhi, Mumbai, Other).

3. **Loading:**
   - Load the routed data into respective target tables (e.g., `USERS_BANGALORE`, `USERS_DELHI`, `USERS_MUMBAI`, `USERS_DEFAULT`).
![image](https://github.com/user-attachments/assets/83a17f9a-d466-4e00-a62e-41468b4252dc)

**Output:**
Target tables contain user experiences grouped by specific locations.
Bangalore:
![image](https://github.com/user-attachments/assets/e707ea79-eb3b-4a76-bfaf-6fc9c86d9e01)
Mumabi:
![image](https://github.com/user-attachments/assets/db3b561f-6c95-4a68-88be-8e500282352e)

Delhi:
![image](https://github.com/user-attachments/assets/961fadbd-75c2-40ff-b0b1-dbaba0e00fe7)
Default:
![image](https://github.com/user-attachments/assets/afdf8efa-5e18-486c-a852-1ff3c77014f2)

 
---

###  Retrieve User Names for Posts Using Lookup Table

**Objective:** Match user IDs from posts with usernames.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `POSTS` and `USERS` tables.

2. **Lookup:**
   - `Lookup` Transformation: Link `USER_ID` from `POSTS` table with usernames from `USERS` table.

3. **Loading:**
   - Load the data into a comprehensive target table showing user names for posts.

**Output:**
The target table contains usernames corresponding to posts.
![image](https://github.com/user-attachments/assets/f4f57e71-c572-44d3-b168-ca1c1261d80a)

---

###  Total Experience of a User in All the Companies

**Objective:** Calculate the total experience of users across all companies.

**Transformation Steps:**
1. **Extraction:**
   - Extract data from `USERS` and `EXPERIENCE` tables.

2. **Calculation:**
   - `Expression` Transformation: Compute the duration of each work experience using `DATEDIFF`.

3. **Aggregation:**
   - `Aggregator` Transformation (`AG`): Sum the total experience duration for each user.

4. **Loading:**
   - Load the total experience data into the `TARGET_TOTAL_EXPERIENCE` table.
![image](https://github.com/user-attachments/assets/5b0fa4d1-bb35-4bee-b1e6-e160a009ae47)

**Output:**
The `TARGET_TOTAL_EXPERIENCE` table shows the total experience for each user.
![image](https://github.com/user-attachments/assets/64ea1d6d-a86a-4a1b-9612-0b516ee14393)


---

## Conclusion

The ETL processes described in this repository offer comprehensive solutions for managing and analyzing user data in a LinkedIn-like platform. By implementing these transformations, organizations can optimize their data operations, enhance user engagement, and drive strategic decision-making.

Feel free to explore and adapt these scenarios to fit your specific requirements.

