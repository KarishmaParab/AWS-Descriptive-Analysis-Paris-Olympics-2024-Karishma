**Descriptive Analysis - Paris Olympics 2024**

**Table of Contents:**

1.	Project Description
2.	Project Title
3.	Objective
4.	Dataset
5.	Tools and Technologies
6.	Methodology
	Step 1: Data Analytical Question Formulation (DAP)
	Step 2: Data Discovery
	Step 3: Data Storage Design
	Step 4: DataSet Preparation
	Step 5: Data Ingestion and Storage
	Step 6: Data ETL Pipeline Design
	Step 7: Data Cleaning and Structuring
	Step 8: Data ETL Pipeline Implementation
	Step 9: Data Analysis
	Step 10: Data Visualization
	Step 11: Data Publishing
	Step 12: Data Protection
	Step 13: Data Governance 
	Step 14: Data Monitoring 
7.	Recommendation
8.	Future Opportunities
9.	Reference

**Project Description: Understanding the Paris Olympic 2024 Gold, Silver, and Bronze medal-winning pattern for top countries.**

**Project Title: Paris Olympic 2024 – Data Analysis – Medalwise.**

**Objective:** The primary goal of this project is to conduct a descriptive analysis of players winning gold, silver, and bronze medals from top countries in the world at the Paris Olympics 2024. Through this analysis, I aim to summarize the key characteristics of players who have won medals in various sports such as basketball, swimming, gymnastics, athletics, fencing, etc. I aim to analyze which sports or events won the most medals and which country dominated specific sports.

**Dataset:**
The dataset includes the following features/columns
•	Country: The name of the country that the athlete or team represent. (Example: USA, China, Canada, etc)
•	Country_Code: A three-letter abbreviation or standardized code used to identify each country. (Example: United States (USA), France (FRA), etc)
•	Sports/Discipline: The category of sport or specific discipline within the Olympics that the medal was awarded in. (Example: Swimming, Gymnastics, etc)
•	Event: The specific competition or event within the sport/discipline where the athlete or team competed and won a medal. (Example: Men’s/Women's Marathon, 100m 		freestyle, etc)
•	Medal_Type: The type of medal won by the athlete or team (Example: Gold, Silver, or Bronze)
•	Player_Name: The name(s) of the athlete(s) who won the medal in the event.
•	Medal_Date: The date when the athlete or team won the medal.

**Tools and Technologies:**

•	AWS (S3, AWS Databrew, AWS Glue, Athena, EC2, Key Management System (KMS), Encryption, Replication, IAM, CloudWatch, CloudTrail)

**Methodology:**

•	**Step 1:** **Data Analytical Question Formulation (DAP)**: The first step is data analytical question formulation (DAP formulation). We have four types of analysis questionnaires: descriptive analysis questions, diagnostic analysis questions, predictive analysis questions, and prescriptive analysis questions. For the Olympic 2024 data, I have chosen a descriptive analysis question, which would calculate the metric “Total Number of Gold, Silver, and Bronze medals achieved by each top country.”

•	**Step 2**: **Data Discovery**: In Step 2, Data Discovery, I used the Kaggle data portal to download the dataset. We have downloaded the dataset for the Olympics 2024, with around 600 records.

**Figure 1: Data Discovery**
 ![image](https://github.com/user-attachments/assets/905edf65-1d94-46a5-81d3-3dca5e45b4ff)


•	**Step 3:** **Data Storage Design:** For Step 3, Data Storage Design, I created a bucket called “olympic2024-analysis-karishma.” Under this bucket, I created a “2024” year folder, and under this folder, I created separate folders such as Landing, Raw, and Curated, Trusted to store the data from different web services in AWS S3.

**Figure 2: Data Storage: Main Bucket**
 ![image](https://github.com/user-attachments/assets/fd8f8993-fdd5-4ca7-8b70-48a340a77611)


**Figure 3: Data Storage: S3 Folder Structure:**
![image](https://github.com/user-attachments/assets/7b178c0a-28f6-4152-bc0e-ba4b241cde93)	

•	**Step 4:** **DataSet Preparation:** For Step 4, Dataset Preparation, the dataset was downloaded for the 2024 year with around 600 records from the Kaggle data portal. After downloading the data from the portal in Excel format, I performed cleaning operations, such as removing extra relevant columns for the analysis. I prepared the data for the next step.

•	**Step 5:** **Data Ingestion and Storage:** In Step 5, Data ingestion and Storage, I uploaded the Olympic2024 data Excel file into the landing folder in AWS S3. I stored the data in a S3 for further use.

**Figure 4: Data Ingestion and Storage in Landing Folder**
![image](https://github.com/user-attachments/assets/f594de7a-4b7f-4c8f-8413-390a916b1c33)


•	**Step 6:** **Data ETL Pipeline Design:** For the Olympic 2024 dataset, I calculated the Total Number of Gold, Silver, and Bronze medals achieved by each top country. For designing the ETL in AWS Glue, I have designed the data lineage diagram to show the steps required to calculate the Total Number of Gold, Silver, and Bronze medals achieved by each top country.


**Figure 5: ETL Pipeline Design**
![image](https://github.com/user-attachments/assets/c5a96644-7127-4482-bc70-a8f8b5aa1044)

 

•	**Step 7:** **Data Cleaning and Structuring:** In Step 7, Data Cleaning and Structuring, I used AWS Data Brew. I performed various steps for data cleaning. First, I checked for any errors in the data; if found, then I removed the errors, renamed the database fields, and corrected the data type for some fields. I also performed other cleaning and structuring activities, such as playing columns as required. After the data is cleaned and structured, I run the job and store the output data in the Raw folder of S3 to use in the next stages.

**Figure 6: Data Cleaning With AWS Glue DataBrew**
![image](https://github.com/user-attachments/assets/0199b193-b686-4d2c-998e-dd95a96a8115)

 
**Figure 7: Aws DataBrew Output stored in Raw Folder**
![image](https://github.com/user-attachments/assets/8b625d57-ec95-4f09-b521-7d97f2fb7e5c)

 
•	**Step 8: Data ETL Pipeline Implementation:** In Step 8, Data Pipeline Implementation, I used AWS Glue to create an ETL pipeline implementation. In this ETL, I used source data from the RAW folder of AWS S3. I used various components for ETL implementation from AWS Glue service, such as change schema, conditional router, aggregate, and SQL query for the data. After the ETL was implemented successfully, I ran this ETL and stored data in the AWS S3 Curated folder.

**Figure 8: ETL Implementation**
![image](https://github.com/user-attachments/assets/8931ec41-531a-4920-8d7d-02d3fd4c2e65)

**Figure 9: AWS ETL Output Stored S3 Curated folder**
![image](https://github.com/user-attachments/assets/5575eb38-c092-4c77-bf1f-12db1050b4fe)

 
•	**Step 9: Data Analysis:** In Step 9, I used AWS Athena to create a database and database table. I selected the S3 folder curated path as a source to fetch records into a table. To create a table, I created columns as per the requirement, which were country, medal achievement year, total gold medals, total silver medals, and total bronze medals. I have created the “olympic_2024_database_karishma” database and the “olympic_2024” table in AWS Athena. With the help of the database and table, I fetched the data from the curated folder, performed SQL query operations on the data, and downloaded the output for the next phase, i.e., data visualization.

**Figure 10: Data Analysis with the help of AWS Athena**
![image](https://github.com/user-attachments/assets/ee36b748-e126-4ce2-a9fc-9cad2eb4c698)

•	**Step 10: Data Visualization**: Basically, in AWS, we have Quicksight AWS service to do the visualization. However, our students' AWS console does not have access to it; hence, we performed data visualization with the help of Excel. In the Previous step (Step 09: data analysis), I generated the output using SQL query, and that output was downloaded in CSV format in AWS Athena. I then used that file to create an Excel graph and exported this file into PDF format for data publishing. With the help of data visualization through Excel, I could analyze which country earned the most medals in the 2024 Olympics.


**Figure 11: Data Analysis**
![image](https://github.com/user-attachments/assets/614c0b27-6238-4c51-98e4-4be21d9f706b)

•	**Step 11: Data Publishing:** In the Data Publishing step, I used Amazon EC2 service to launch two server instances: General and Web servers. On the General Server, we used Microsoft Remote Desktop to transmit the CSV output and PDF files using the shared RDP credentials. We deployed IIS (Internet Information Services) on the Web Server using AWS EC2 server management tools. Following installation, we saved the Graph_Report.pdf, CSV file, and index.html files to the C drive directory created by IIS. We accessed and fetched the reports using the Web Server's IP address, which allowed us to view the data in graph format. This structure ensured that the processed data was successfully published and readily available for additional study.

**Figure 12: EC2 : Web Server Instance Creation**
![image](https://github.com/user-attachments/assets/35d8d6b4-445f-417f-b4d0-ef055be04275)

 

**Figure 13: Data Publishing with EC2**
![image](https://github.com/user-attachments/assets/f439a066-ac8c-4229-a93a-b9764abe2c96)

 

•	**Step 12: Data Protection**: In this project, I have used AWS IAM and KMS services to control user access and encrypt the data at rest and in transit. I have also used replication rules in the S3 for data backup, availability, and integrity purposes. I created a role (Labrole) with specific permissions to manage and safeguard the Olympics data. Next, I used AWS Key Management Service (KMS) to generate a secure encryption key. This key was assigned to the Labrole for administrative and operational purposes, guaranteeing that data can only be accessed through approved actions. The KMS key adds extra protection by encrypting datasets, ensuring data integrity and confidentiality.

**Figure 14: Data Protection with KMS**
![image](https://github.com/user-attachments/assets/cf759eac-7ea0-4975-8e23-51a644859b25)


**Figure 15: Key Information**
![image](https://github.com/user-attachments/assets/77361622-17ce-42a8-866f-d20e52fceae3)

**Figure 16: Data Encryption (S3 Bucket) with KMS**
![image](https://github.com/user-attachments/assets/3b6ced25-1ee5-4f25-9d16-6655b8ce2c63)


**Figure 17: S3 Bucket Data Replication**
![image](https://github.com/user-attachments/assets/ba2b0ef3-3e19-4efa-8014-2727b5ce7cbe)


•	**Step 13: Data Governance**: 
AWS Data Governance refers to the processes, policies, and frameworks that help to manage and control the cloud environment. It ensures that using AWS resources aligns with the organization's business objectives, regulatory requirements, and best practices for security, compliance, and cost management. I have used AWS Glue to design the ETL for Data Privacy and Data Quality check rules, checking the files from the Raw folder, processing them using the rules, and storing the results in the Trusted folder for further analysis. In this project for data privacy, I checked for sensitive data using seven features provided by AWS for Canada, such as sin number, bank account, etc., to verify the data privacy in our data set as the first step in the ETL. 
Once the privacy check is passed and sensitive data is masked, I check for data quality and check if the medal (gold, silver, bronze) medal has 95% completeness. Otherwise, it is not helpful for further analysis. After that, I segregated the passed and failed data separately using a conditional router; I stored the passed data in the trusted folder after removing the additional columns generated by the quality check step. I have also prepared the schedule and workflow in case this check needs to run automatically every week.

**Figure 18: Data Governance with the help of the Data Quality ETL implementation**
![image](https://github.com/user-attachments/assets/26809d76-419f-48be-939f-93f8fd30aca0)


**Figure 19: Workflow Creation**
![image](https://github.com/user-attachments/assets/3297291a-dc8b-4000-81b7-fe19dbcac3c2)


**Figure 20: Workflow Scheduling**
![image](https://github.com/user-attachments/assets/76c7cea0-c4d6-4779-98dc-b7d5f48cb5b8)
	 
	
•	**Step 14: Data Monitoring:** 
AWS Data monitoring refers to continuously observing and tracking data flows, system performance, resource usage, and security within an AWS environment. Data monitoring ensures data integrity, availability, security, and compliance while optimizing performance and costs. I have used the AWS CloudWatch service to prepare the monitoring and control dashboard. The property tax dashboard shows estimated charges, the number of objects in the S3 bucket, and an alarm for billing if the budget exceeds $35. 
I have also used AWS CloudTrail service based on the requirement of logging the user information, as the management would like to know the information regarding who has made what changes in the environment as it provides visibility into changes to resources and potential security threats. The logs generated by CloudTrail are stored in a new S3 bucket, and we have also encrypted this bucket as logs are very sensitive data, and we would like to protect them.
	
**Figure 21: AWS CloudWatch Dashboard Creation**
![image](https://github.com/user-attachments/assets/0e60a341-4702-4e69-8588-2a264de5479f)
 
**Figure 22: AWS CloudWatch Alarm Creation**	 
![image](https://github.com/user-attachments/assets/1313feda-7ff6-4cf2-9b01-13a50f61f6aa)

**Figure 23: AWS CloudWatch Dashboard with Alarm and other Metrics**	 
![image](https://github.com/user-attachments/assets/181fe12b-2579-40d1-8c95-133697d00ba3)
	
**Figure 24: AWS CloudTrail**	 
![image](https://github.com/user-attachments/assets/9bad3d81-ad7c-4879-a6ee-f5e621e04396)

**Recommendations:**

•	Low-Performing Countries: This project can help low-performing countries better understand which sports they failed to achieve many medals in. With the help of this information, low, low-performing countries can work on those sports which they lack and can promote such sports in their country for new participation; countries can train new candidates in these sports and can achieve good results in next year's Olympic event. They can invest in sports infrastructure, coaching, and athlete development programs.

•	High High-Performing Countries: This project can help high-performing countries understand which game their country played well and achieve the highest number of gold, silver and bronze medals. They can continue funding sports infrastructure, cha-ching, athlete development programs, and strengthening talent programs in both high-performing schools as well as poorly performed schools. These high-performing countries can also invest in new sports in Olympic events and train their athletes for them, allowing them to achieve good results in such new sports as well. 

**Future Opportunities:**

•	Predictive Analytics: Use current data to predict future medal winners or emerging countries in certain sports.
•	Data Sharing and Collaboration: Encourage collaboration between countries, coaches, and athletes through data sharing for improved performance.
•	Enhancing Athlete Development Programs: Recommend using medal data to refine scouting, training, and support for emerging talents.

**Reference:**

Petro. (2024, September 01). Paris 2024 Olympic Summer Games. Kaggle.
https://www.kaggle.com/datasets/piterfm/paris-2024-olympic-summer-games


