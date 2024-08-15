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
