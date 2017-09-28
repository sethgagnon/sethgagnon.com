---
title: 'Enabling the Purge & Archive Service in Business Monitor 8.0.1.1'
author: Seth
type: post
date: 2014-04-24T16:00:41+00:00
url: /enabling-purge-archive-service-business-monitor-8-0-1-1/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor
tags:
  - archive
  - business monitor
  - IBM Business Monitor
  - instance
  - instances
  - monitor
  - monitor model
  - performance
  - purge
  - 'purge &amp; archive'

---
The following italicized excerpt is from the IBM InfoCenter for IBM Business Monitor 8. This is the direct content as written by IBM:

<a href="http://pic.dhe.ibm.com/infocenter/dmndhelp/v8r0m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fdata%2Fpurgearchive_instdata_manage.html" target="_blank">IBM Infocenter for Enabling Purge & Archive Service  for Monitor 8</a>

Per IBM:

To maintain dashboard performance and ensure that your system runs efficiently, you can purge, archive, export, and import instance data for a monitor model version.
  
The following scenarios explains the benefits of the purging and archiving function:
  
Scenario one:

  * Your IBM® Business Monitor server has run for a long period of time.
  * The dashboard becomes slow due to the amount of data.
  * You archive data on a one-time or periodic basis.
  * The dashboard&#8217;s performance improves because there is less data to report on.
  * Optionally, you can move the archived data to an environment dedicated to historical analysis or to a data warehouse.

Scenario two:

  * You have run the monitor model for a period of time and have some terminated instances and some active instances.
  * You show the dashboard with the existing terminated and active instances, and are satisfied with the results.
  * You export the terminated and active instances into the flat files as the backup.
  * You want to show the same dashboard later, and so you import the instances.

You can purge instance data and archive it on a one-time basis or set it up as a scheduled service.
  
Scheduled service can be found under Applications > Monitor Services > Monitor Model > Scheduled Services > Purge and Archive Instance Data. Here you can set up the frequency of running the service.

[<img class="alignnone size-full wp-image-1102" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service.png?resize=900%2C557" alt="Purge & Archive Instance Service" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service.png?w=941 941w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service.png?resize=300%2C185 300w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" />][1]

Click on Version > Model Version. Here you can set up the data you want to purge based on a given number of days, as well as, the location of where to create the CSV files that will contain the purged data.

[<img class="alignnone size-full wp-image-1104" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service-2.png?resize=900%2C510" alt="Purge & Archive Instance Service 2" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service-2.png?w=926 926w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service-2.png?resize=300%2C170 300w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" />][2]

 [1]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service.png
 [2]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/04/Purge-Archive-Instance-Service-2.png