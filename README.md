# Monitoring and Analyzing Logs with Microsoft Sentinel
Monitoring and analyzing logs is a key part of security operations. In this project, I used Microsoft Sentinel, which includes Log Analytics, a powerful tool that allows me to edit and run queries on collected data and interactively analyze the results. These queries are written in _Kusto Query Language (KQL)_, a flexible and efficient language for querying and visualizing data.

### This is what I will learn in this project:

Learning how to use the Log Analytics tool within Microsoft Sentinel.
Gaining hands-on experience running KQL queries to analyze and interpret log data.
By practicing these skills, I aim to better understand how to detect patterns, spot anomalies, and gain actionable insights to improve security operations.

### Step 1: Log in to Azure Portal<br />

1. Open the Azure Portal.<br />
2. Use the credentials provided:<br /> 
    - Username: john.doe@onmicrosoft.com<br />
    - Password: FakePassword!0
---
### Step 2: Access Microsoft Sentinel Workspace
1. In the Azure Portal, I navigated to my created workspace:<br />
    - Workspace: nemuel-ms-sentinel-log-analytics-fgthsjgwveh<br />
2. Note: You cannot directly log in to Microsoft Sentinel. Always open the workspace through the Azure Portal.<br />

<img width="1200" alt="Sentinel 1" src="https://github.com/user-attachments/assets/ed6c927f-d9f6-4c90-9aec-ec81dfc26cde" />

---
### Step 3: Open Log Analytics
1. In the workspace, I went to General > Logs.<br />
2. A Welcome to Log Analytics message may appear. You can:<br />
    - Explore the information about Log Analytics and Kusto Query Language (KQL).<br />
    - Skip and close the welcome screen.<br />
3. Disable the pop-up if prompted.<br />

<img width="1200" alt="Sentinel 2" src="https://github.com/user-attachments/assets/72133674-8c64-4d14-9f3b-d8ae7538d1e9" />

---
### Step 4: Explore the Log Analytics Tool
1. You should now see the Log Analysis Tool interface.<br />
2. Key features to note:<br />
    - Use the Run button to execute queries.<br />
    - Use the toolbar to specify the time range for logs.<br />
3. On the left-hand side, expand the Schema and filter pane to view:<br />
    - Tables grouped by solutions.<br />
    - Queries and functions available for analysis.<br />

<img width="809" alt="Sentinel 3" src="https://github.com/user-attachments/assets/8eb6f02b-b4ce-41f4-ae1a-04bd26c55437" />
<img width="1132" alt="Sentinel 4" src="https://github.com/user-attachments/assets/374f9a4d-cf27-4970-834d-f16671faf72c" />

---
# Kusto Query Language (KQL)<br />
Kusto Query Language (KQL) is used in Microsoft Sentinel for analyzing data. KQL is a read-only language — it cannot create, edit, or delete data. KQL is inspired by SQL, and data is organized into:
    - Databases<br />
    - Tables<br />
    - Columns<br />
Queries in KQL consist of statements separated by semicolons.

### Types of KQL Statements<br />

1. Let Statements<br />
    - Used to define variables that can be used in later parts of the query.<br />
2. Tabular Expression Statements<br /> 
    - Used to query data from tables and apply operations like filtering, summarizing, and sorting.
---
# Query Logs in Microsoft Sentinel<br />
In this step, I will examine the Security Datasets logs, which have been preloaded into the SIEM using Microsoft Sentinel To-Go. This open-source project simplifies the deployment of Microsoft Sentinel labs for research purposes.

The logs are stored in the _prerecorded_CL_ table.<br/>

---
### Step 5: Set the Custom Time Range
1. Open the Log Analytics tool in Microsoft Sentinel.<br />
2. Set a custom time range:<br />
Kusto Query Language (KQL) is used in Microsoft Sentinel for analyzing data. KQL is a read-only language — it cannot create, edit, or delete data. KQL is inspired by SQL, and data is organized into:
    - End: Now<br />
    
<img width="827" alt="Sentinel 5" src="https://github.com/user-attachments/assets/49295c5d-7c02-4481-9a50-9704f85bf424" />

---
### Step 6: Query All Logs
1.To query all the logs in the _prerecorded_CL_ table, use the following KQL query:<br />
<img width="709" alt="Screenshot 2024-12-16 at 11 53 56 PM" src="https://github.com/user-attachments/assets/b290c82d-3030-4d6f-bc86-4d0eaf54bfed" />
### Note: <br/>
Querying the entire table can return a large number of results, which may slow down processing.

---
### Step 7: Limit the Results
To make the query more efficient, limit the number of results using the take or limit keyword. For example, to retrieve the first 10 rows, use:<br />
<img width="1012" alt="Sentinel 6" src="https://github.com/user-attachments/assets/6c7924f7-c011-46c7-992f-c358d5735a06" />

1. Run the query.<br />
2. Expand any row in the results by clicking the arrow button on the left to inspect the details.<br />
<img width="1390" alt="Sentinel 7" src="https://github.com/user-attachments/assets/71cd92cb-e2f8-495b-af63-da151b7dd8f0" />

### Step 8: Check the Data Size
To get an idea of the table size, use the count operator to query the number of rows in the table:<br />
prerecorded_CL  
| count

1. Run the query to see the total number of rows in the table.<br />
2. Record the result for analysis.

<img width="1390" alt="Sentinel 8" src="https://github.com/user-attachments/assets/93d8adaa-ddc6-4d7f-b8c1-d9838482e2a6" />

### Project Summary

## Objective
This project focuses on using Microsoft Sentinel and Log Analytics to monitor and analyze security logs. By leveraging Kusto Query Language (KQL), I performed data queries to identify and analyze relevant security insights, while also gaining hands-on experience with key Sentinel tools and workflows.

---

### Key Steps<br/>
1. ### Accessing Microsoft Sentinel Workspace<br />
    - Logged into the Azure Portal and navigated to the Microsoft Sentinel workspace to access preloaded logs.<br />
2. ### Exploring Log Analytics<br /> 
    - Opened the Logs section under Sentinel’s General tab to use the Log Analytics tool for querying data.<br />
3. ### Querying Logs with KQL<br /> 
    - Used KQL queries to analyze logs stored in the prerecorded_CL table, including:<br />
        - Limiting results with take or limit commands.<br />
        - Counting records in the table with the count keyword.<br />
    - Customized time ranges to filter and examine log data more efficiently.<br />
4. ### Learning Kusto Query Language (KQL)<br />
    - Applied KQL to write queries that filtered, summarized, and sorted data.<br />
    - Learned about core KQL concepts, such as let statements, tabular expressions, piping (|), and various data types (e.g., dynamic, timespan).<br />
---
### Deliverables

- ### KQL Queries:<br />
    - Examples of queries used to retrieve, filter, and summarize log data.<br />
- ### Screenshots:<br /> 
    - Captured key steps for navigating Sentinel, opening the Logs tool, and executing queries.<br />
- ### Documentation:<br /> 
    - Overview of Microsoft Sentinel, Log Analytics, and KQL concepts.<br />
    - Answers to project questions about KQL statements, data types, and operators.
---
### Conclusion

This project provided valuable experience with Microsoft Sentinel and Kusto Query Language (KQL) for security log analysis. By querying logs and interpreting results, I developed skills essential for monitoring and responding to security events in real-world scenarios.
