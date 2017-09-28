---
title: Enabling the Data Movement Service for IBM Business Monitor 8.0.1
author: Seth
type: post
date: 2014-04-22T21:47:08+00:00
url: /enabling-data-movement-service-ibm-business-monitor-8-0-1/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor
tags:
  - BAM
  - business monitor
  - data movement service
  - DMS

---
The following italicized excerpt is from the IBM InfoCenter for IBM Business Monitor 8. This is the direct content as written by IBM:

<a href="http://pic.dhe.ibm.com/infocenter/dmndhelp/v8r0m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fdata%2Fdms.html&resultof%3D%2522%2564%2561%2574%2561%2522%2520%2522%256d%256f%2576%2565%256d%2565%256e%2574%2522%2520%2522%2573%2565%2572%2576%2569%2563%2565%2522%2520%2522%2573%2565%2572%2576%2569%2563%2522%2520" target="_blank">IBM Infocenter for Enabling DMS for Monitor 8</a>

Per IBM:

_Data movement service optimizes server processing and reporting in higher volume production environments. Operational tables are optimized for inserts and updates, and the reporting tables are optimized for dashboard queries. When enabled, data movement service runs automatically as a scheduled service. Once enabled, data movement service cannot be disabled. Data movement service is optional in this release. It is not recommended for development and test environments, or small production environments where performance is not a concern. Therefore, it is not supported in the unit-test environment (UTE), also referred to as the Integrated Test Environment (ITE)._

_The copying and pruning operations of data movement service are handled by SQL stored procedures created in the database when data movement service is enabled. Data movement service can be enabled for a version of a model when it is deployed. It can also be deferred to a later time. It can be enabled by selecting **Enable DMS** at the WebSphere Application Server administrative console or by exporting the DDLs to be run manually._

_**Note:**_

  * _If you are using Oracle as your database, export and manually run the database scripts to enable data movement services. These scripts include commands that create and drop tables and views and are not transactional with Oracle. If the scripts fail to complete successfully, the database administrator must perform any required cleanup because rollback is not supported. DB2 is fully transactional and running the scripts automatically on DB2 is acceptable if your database administrator allows it._
  * _If you are using DB2® on zOS you must export the scripts and run them manually._
  * _The server database user must have administrative privileges to create database objects. For more information, refer to the topic &#8220;Securing the data movement service database schema.&#8221; A related link is provided._

_Data movement service automates the copying and pruning operations. Data movement service schedules stored procedures to run at regular intervals. You can control the invocation of the data movement service stored procedures and the data movement service interval. The data movement service also provides a log that contains a record of the details of the stored procedure invocations._

_The data movement service historical logs are recorded in the DMS\_HISTORY\_T table in the Monitor database. Each record in the table contains information about the model name, the model version, the monitoring context, the configured interval, rows copied to the reporting table, rows pruned from the operational tables. It also has a message indicating the status from the execution of the associated stored procedure, the last time the stored procedure was invoked, and the last time the stored procedure completed execution._

&nbsp;

**<span style="text-decoration: underline;">Some general notes, as recommended by me</span>**:
  
• The frequency you set for the running of the service, i.e. every five minutes, will determine how often the data is refreshed in the dashboard. You will need to ensure that your business users provide some requirements around this delay.
  
• If using KPIs, it is important that the KPI caching be set to the same value as the frequency in running DMS, or greater. For example, if your DMS service runs every five minutes, then the KPI cache refresh needs to be set to 5 minutes are greater.
  
• Understanding your event delivery frequency is important when trying to determine if your monitor model should be using the Data Movement Service. A good rule of thumb is any monitor model receiving more than 100 events/second should enable the Data Movement Service.

&nbsp;

To enable the DMS for you Monitor Model, you have two options:

1) When installing the Monitor Model, you can select a check box that will create the DMS tables for you as part of the monitor model installation. This can be done if you have not changed any of the default table names or structure when you installed and configured Business Monitor. Simply select the check box on Step 12 of the Detailed Installation of the model highlighted in red in the figure below.

[<img class="alignnone size-full wp-image-1088" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-with-MM-Install.png?resize=900%2C729" alt="Enable DMS with MM Install" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-with-MM-Install.png?w=988 988w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-with-MM-Install.png?resize=300%2C242 300w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" />][1]

&nbsp;

2) This second option works after you have already installed the Monitor model. First <span style="text-decoration: underline;">Stop</span> your monitor model. You simply navigate to Applications > Monitor Models > _Monitor Model Version_ > Enable Data Movement Service. From here, you have two actions: 1) Run Enable DMS Script &#8211; which will perform the same operations as in the previous option above. This cannot be used if you have different table names and structures. And 2) Export Enable DMS script &#8211; which will produce the SQL that you can provide to your DBAs (or yourself if you have access) to edit so that it executes against the right schemas and tables.

[<img class="alignnone size-full wp-image-1091" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-after-Installed.png?resize=900%2C242" alt="Enable DMS after Installed" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-after-Installed.png?w=991 991w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-after-Installed.png?resize=300%2C80 300w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" />][2]

After the script has been successfully executed, you may start your model back up.

 [1]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-with-MM-Install.png
 [2]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Enable-DMS-after-Installed.png