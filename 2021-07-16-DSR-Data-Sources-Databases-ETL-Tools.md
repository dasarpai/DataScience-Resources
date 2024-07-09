---
id: 116    
title: "Navigating the Data Landscape: Exploring Data Sources, Databases, and ETL Tools for Machine Learning Projects"
permalink: /dsblog/navigating-the-data=landscape
date: 2021-07-16
tags: [DS Resources, Data Sources, Databases, ETL Tools] 
categories: 

header:
   teaser: /assets/images/dspost/dsr116-Data-Sources-Databases-ETL-Tools.jpg
author: Hari Thapliyaal   
mathjax: "true"
share: true
excerpt:   
layout: dspost-layout   
author_profile: true   
toc: true   
toc_sticky: true 
---

![Data Sources, Databases, ETL Tools](/assets/images/dspost/dsr116-Data-Sources-Databases-ETL-Tools.jpg)      

# Navigating the Data Landscape: 
**Exploring Data Sources, Databases, and ETL Tools for Machine Learning Projects**

## Introduction

Data sources: Data sources refer to the origins or locations from which data is collected or generated. They can include various platforms, systems, devices, or applications that generate or store data, such as databases, APIs, files, sensors, social media platforms, or web services.

Databases: Databases are organized collections of structured data that are stored, managed, and accessed using database management systems (DBMS). They provide a structured way to store and retrieve data efficiently, enabling data storage, retrieval, manipulation, and querying operations for various applications.

ETL tools: ETL stands for Extract, Transform, Load. ETL tools are software applications or platforms designed to facilitate the extraction, transformation, and loading of data from multiple sources into a target destination, such as a data warehouse or database. These tools help automate and streamline the process of collecting data from diverse sources, performing data transformations or cleansing, and loading the processed data into a centralized storage or analytics platform.

Machine learning projects require various types of data, such as text, image/video, tabular, or voice/music. These data may be divided into timeseries or non-timeseries data, as well as stored, live/stream, or real-time data depending on liveness. Volume may range from a few megabytes to several petabytes/exabytes per day, depending on the data's source. Managing such varied data types, volumes, and liveness requires different technologies for storage, access, transmission, processing, and analysis, of which hundreds are available.

Extracting data from a range of prototypes, technologies, and security systems is difficult due to the differing connectors, authentications, and authorizations required. This article aims to present various data format/data storage/data management technologies that can be applied in a data science project, which can include databases, data sources, and ETL tools. It is unlikely that any single project would require all these systems/technologies, but it is essential to have an overview of the available technologies and their complexity of data processing, storage, transmission, and analysis, particularly when dealing with multiple technologies simultaneously.

Finally, a list of over 200+ data sources, databases, and ETL tools is provided, each with distinctive features for handling specific data types, scale, security, and performance requirements.

## List of Data Technologies

|Sno | Name | Category
|--- |--- |---
|1 | Act CRM | CRM & ERP
|2 | Active Directory | COLLABORATION
|3 | Acumatica | CRM & ERP
|4 | Adobe Analytics | MARKETING
|5 | ADP | ACCOUNTING
|6 | Airtable | COLLABORATION
|7 | Alfresco | COLLABORATION
|8 | Amazon Athena | BIG DATA & NOSQL
|9 | Amazon Aurora | RDBMS
|10 | Amazon DynamoDB | BIG DATA & NOSQL
|11 | Amazon Marketplace | E-COMMERCE
|12 | Amazon RDS | RDBMS
|13 | Amazon Redshift | BIG DATA & NOSQL
|14 | Amazon S3 | FILE & API
|15 | Apache Avro | FILE & API
|16 | Apache Cassandra | BIG DATA & NOSQL
|17 | Apache H Base | BIG DATA & NOSQL
|18 | Apache Hive | BIG DATA & NOSQL
|19 | Apache Impala | RDBMS
|20 | Asana | COLLABORATION
|21 | Authorize.Net | E-COMMERCE
|22 | Autify | COLLABORATION
|23 | Avalara Avatax | ACCOUNTING
|24 | AWS Management | COLLABORATION
|25 | Azure Analysis Services | RDBMS
|26 | Azure Cosmos DB | BIG DATA & NOSQL
|27 | Azure Data Catalog | BIG DATA & NOSQL
|28 | Azure Data Lake Storage | BIG DATA & NOSQL
|29 | Azure Management | COLLABORATION
|30 | Azure Synapse | RDBMS
|31 | Basecamp | COLLABORATION
|32 | Big Commerce | E-COMMERCE
|33 | Blackbaud | ACCOUNTING
|34 | Box | FILE & API
|35 | Bugzilla | COLLABORATION
|36 | Bullhorn CRM | CRM & ERP
|37 | Casandra | Non Relational Data Storage
|38 | CockroachDB | BIG DATA & NOSQL
|39 | Confluence | COLLABORATION
|40 | Couchbase | BIG DATA & NOSQL
|41 | CSV | FILE & API
|42 | Databricks | BIG DATA & NOSQL
|43 | DataRobot | COLLABORATION
|44 | DBVisualizer | Relational Data Storage
|45 | Digital Ocean | FILE & API
|46 | DocuSign | COLLABORATION
|47 | Dropbox | FILE & API
|48 | Dynamics 365 FinOps | CRM & ERP
|49 | Dynamics Business Central | CRM & ERP
|50 | Dynamics GP | ACCOUNTING
|51 | Dynamics Nav | ACCOUNTING
|52 | eBay | E-COMMERCE
|53 | Edgar Online | E-COMMERCE
|54 | ElasticSearch | BIG DATA & NOSQL
|55 | Email | COLLABORATION
|56 | EnterpriseDB | Relational Data Storage
|57 | EnterpriseDB | RDBMS
|58 | Epicor ERP | CRM & ERP
|59 | ETL Greenplum | RDBMS
|60 | Evernote | COLLABORATION
|61 | Exact Online | CRM & ERP
|62 | Facebook Ads | MARKETING
|63 | FedEx | E-COMMERCE
|64 | Financial Force | CRM & ERP
|65 | Freshbooks | ACCOUNTING
|66 | Freshdesk | ACCOUNTING
|67 | Github | COLLABORATION
|68 | Gmail | COLLABORATION
|69 | Google Ads | MARKETING
|70 | Google Analytics | MARKETING
|71 | Google BigQuery | BIG DATA & NOSQL
|72 | Google Calendar | COLLABORATION
|73 | Google Cloud Storage | FILE & API
|74 | Google Contacts | COLLABORATION
|75 | Google Data Catalog | BIG DATA & NOSQL
|76 | Google Dataset | 
|77 | Google Drive | FILE & API
|78 | Google Sheets | COLLABORATION
|79 | Google Spanner | BIG DATA & NOSQL
|80 | GraphQL | BIG DATA & NOSQL
|81 | Harper DB | BIG DATA & NOSQL
|82 | HDFS | FILE & API
|83 | Highrise | CRM & ERP
|84 | HPCC Systems | BIG DATA & NOSQL
|85 | HubSpot | MARKETING
|86 | IBM Cloud Objectz | BIG DATA & NOSQL
|87 | IBM Cloud SQL Query | FILE & API
|88 | IBM Cloudant | BIG DATA & NOSQL
|89 | IBM Db2 | RDBMS
|90 | Instagram Ads | MARKETING
|91 | JDBC-ODBC Bridge | RDBMS
|92 | Jira by Atlassian | COLLABORATION
|93 | Jira Service Desk | COLLABORATION
|94 | JSON | FILE & API
|95 | Kintone | COLLABORATION
|96 | LDAP | FILE & API
|97 | LinkedIn Ads | MARKETING
|98 | Log Files from OS | FILE & API
|99 | Magento | E-COMMERCE
|100 | MailChimp | MARKETING
|101 | MariaDB | RDBMS
|102 | Marketo | MARKETING
|103 | MarkLogic | BIG DATA & NOSQL
|104 | Microsoft Ads | MARKETING
|105 | Microsoft Dynamics 365 Sales | CRM & ERP
|106 | Microsoft Excel | FILE & API
|107 | Microsoft SQL Server | RDBMS
|108 | Microsoft Teams | COLLABORATION
|109 | MongoDB | BIG DATA & NOSQL
|110 | MongoDB Atlas | BIG DATA & NOSQL
|111 | MS Access | RDBMS
|112 | MS CDS | FILE & API
|113 | MS Exchange Connector | COLLABORATION
|114 | MS OneDrive | FILE & API
|115 | MS OneNote | COLLABORATION
|116 | MS Planner | COLLABORATION
|117 | MS Project | COLLABORATION
|118 | MYOB | ACCOUNTING
|119 | MySQL | RDBMS
|120 | Neo4J | Non Relational Data Storage
|121 | NetSuite | CRM & ERP
|122 | OData | FILE & API
|123 | Odoo | CRM & ERP
|124 | Open Exchange Rates | E-COMMERCE
|125 | Oracle | RDBMS
|126 | Oracle DB | Relational Data Storage
|127 | Oracle Eloqua | MARKETING
|128 | Oracle Sales Cloud | MARKETING
|129 | Parquet | FILE & API
|130 | Paypal | ACCOUNTING
|131 | PDF | FILE & API
|132 | Pinterest | MARKETING
|133 | PostgreSQL | RDBMS
|134 | Presto | BIG DATA & NOSQL
|135 | Presto DB | BIG DATA & NOSQL
|136 | Quandl | E-COMMERCE
|137 | Quickbase | COLLABORATION
|138 | QuickBooks Online | ACCOUNTING
|139 | Reckon | ACCOUNTING
|140 | Redis | BIG DATA & NOSQL
|141 | RedisDB | Non Relational Data Storage
|142 | REST | FILE & API
|143 | RSS | FILE & API
|144 | Sage 300 | CRM & ERP
|145 | Sage | ACCOUNTING
|146 | Salesforce | CRM & ERP
|147 | Salesforce Chatter | MARKETING
|148 | SAP Business One DI | CRM & ERP
|149 | SAP Business One | RDBMS
|150 | SAP BusinessObjects BI | COLLABORATION
|151 | SAP ByDesign | CRM & ERP
|152 | SAP Concur | ACCOUNTING
|153 | SAP ERP | CRM & ERP
|154 | SAP Fieldglass | E-COMMERCE
|155 | SAP HANA | RDBMS
|156 | SAP HANA XS Advanced | RDBMS
|157 | SAP Hybris c4c | RDBMS
|158 | SAP Netweaver | CRM & ERP
|159 | SAP Success Factors | COLLABORATION
|160 | SAS Datasets | BIG DATA & NOSQL
|161 | SAS xpt | FILE & API
|162 | SendGrid | MARKETING
|163 | ServiceNow | CRM & ERP
|164 | SFTP | FILE & API
|165 | SharePoint | COLLABORATION
|166 | ShipStation | E-COMMERCE
|167 | Shopify | E-COMMERCE
|168 | Slack | COLLABORATION
|169 | Smartsheet | COLLABORATION
|170 | Snowflake | BIG DATA & NOSQL
|171 | Splunk | MARKETING
|172 | SQL Analysis Services | RDBMS
|173 | Square | E-COMMERCE
|174 | Streak | CRM & ERP
|175 | Sugar CRM | CRM & ERP
|176 | Suite CRM | CRM & ERP
|177 | SurveyMonkey | MARKETING
|178 | Sybase IQ | RDBMS
|179 | Sybase | RDBMS
|180 | Tally | CRM & ERP
|181 | TaxJar | ACCOUNTING
|182 | Teradata | RDBMS
|183 | Trello | COLLABORATION
|184 | Trino | BIG DATA & NOSQL
|185 | Tsheets | ACCOUNTING
|186 | TSV | FILE & API
|187 | Twilio | FILE & API
|188 | TXT | FILE & API
|189 | UPS | E-COMMERCE
|190 | USPS | E-COMMERCE
|191 | Veeva | CRM & ERP
|192 | Wasabi | FILE & API
|193 | WordPress | COLLABORATION
|194 | Workday | ACCOUNTING
|195 | X-Cart | E-COMMERCE
|196 | xBase | RDBMS
|197 | Xero | ACCOUNTING
|198 | Xero Workflow Max | COLLABORATION
|199 | XML | FILE & API
|200 | YouTube Analytics | MARKETING
|201 | Zendesk | COLLABORATION
|202 | Zip Files | FILE & API
|203 | Zoho Books | ACCOUNTING
|204 | Zoho CRM | CRM & ERP

## Conclusion:

In the ever-expanding landscape of data-driven technologies, understanding and harnessing the power of data sources, databases, and ETL tools are crucial for successful machine learning projects. This article has provided a good summary list for data science.

We delved into the concept of data sources, highlighting their diverse nature and the wide array of platforms, systems, and applications that contribute to the data ecosystem. Recognizing the origins and types of data is essential for sourcing relevant and reliable datasets that drive machine learning models forward.

Additionally, we examined the significance of ETL tools, which streamline the extraction, transformation, and loading of data from multiple sources into centralized destinations. These tools automate the data integration process, ensuring that valuable insights can be derived from diverse and complex datasets.

Machine learning projects demand a careful consideration of data types, volumes, liveness, and technological requirements. By understanding the available data storage, management, and processing technologies, data scientists can make informed decisions that align with project objectives and ensure optimal performance.

To aid readers in their data science endeavors, we provided a comprehensive list of over 200+ data sources, databases, and ETL tools. Each entry display the category of technology.
