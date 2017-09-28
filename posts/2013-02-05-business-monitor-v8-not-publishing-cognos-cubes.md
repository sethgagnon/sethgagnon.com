---
title: Business Monitor V8 Not Publishing Cognos Cubes
author: Seth
type: post
date: 2013-02-05T16:23:52+00:00
url: /business-monitor-v8-not-publishing-cognos-cubes/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor

---
If you have setup and configured a network deployment environment of IBM Business Monitor V8 with horizontal clustering across multiple nodes using a remote database, it is important to note that the database client needs to be installed on every server where Cognos is installed. You may see this error as a result of the database client not being configured correctly:

CWMAX4204E: The Cognos cubes created (optional) step failed.
  
CWMLC0113E: Model [JKInsuranceMonitoringModel] version [2013-01-08T15:
  
26:26] step [createCognosCubes] failed. Cause: [CWMTC2210E: It was not
  
possible to create the Cognos cube because the following error
  
occurred: QE-DEF-0285 The logon failed. CWMTC2261E: The database logon
  
failed. Ensure that a local database client is installed on the Cognos
  
server and that the MONITOR database is cataloged. The cataloged name
  
must match the database name configured in the Cognos data source for
  
the Monitor database.].

There is a way to bypass using the native database client and use the JDBC connection that exists in your Monitor cell. To bypass using the native database client, you need to add the following Generic JVM arugment to your Deployment Manager:

-Dinit.dqm.enabled=true

[<img class="alignnone size-full wp-image-1034" alt="Monitor JVM Arg" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2013/02/Monitor-JVM-Arg.png?resize=900%2C490" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2013/02/Monitor-JVM-Arg.png?w=1604 1604w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2013/02/Monitor-JVM-Arg.png?resize=300%2C163 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2013/02/Monitor-JVM-Arg.png?resize=1024%2C557 1024w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" />][1]

After you have saved this argument, you can restart your Business Monitor cell and you should then be able to successfully publish Cognos cubes.

 [1]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2013/02/Monitor-JVM-Arg.png