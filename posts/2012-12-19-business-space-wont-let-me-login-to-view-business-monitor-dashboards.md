---
title: Business Space Won’t Let Me Login to View Business Monitor Dashboards
author: Seth
type: post
date: 2012-12-19T20:32:28+00:00
url: /business-space-wont-let-me-login-to-view-business-monitor-dashboards/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor
  - Business Space
tags:
  - business monitor
  - business space
  - dashboard
  - failed
  - login
  - monitor
  - websphere

---
Were you able to login to your Business Space console to view dashboards that were created on Business Monitor, and now you get a Page Cannot Be Displayed and in your url bar it direct you to a security check (see image below), even though you did not make any changes? If so, read on.

<a href="http://www.sethgagnon.com/business-space-wont-let-me-login-to-view-business-monitor-dashboards/bam-error/" rel="attachment wp-att-983"><img class="alignnone size-large wp-image-983" alt="bam error" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/12/bam-error-1024x640.png?resize=600%2C375" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/12/bam-error.png?resize=1024%2C640 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/12/bam-error.png?resize=300%2C187 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/12/bam-error.png?w=1280 1280w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" /></a>

<!--more-->

Apparently there is a bug that allows duplicate entries to be created in a table in Business Monitor that stores your account information. If this is happening, you will see the following error in your SystemOut.log for your Business Space server:

12/13/12 10:51:23:182 EST] 00000038               E com.ibm.mm.server.
  
persistence.rdbms.dao.ibatis.BaseDao getAccountByExternalId [12/13/12
  
10:51:23:323 EST] 00000038               W com.ibm.mm.server.model.
  
persist.NLFModelPersistenceHandlerImpl loadSharedRoot IGNORING
  
EXCEPTION (error reading account with external id
  
05ebab275936e94ca69d576c67bc8f8d), RETURNING NULL
  
com.ibm.mm.framework.persistence.
  
exceptions.DataBackendException: error reading account with external id
  
<span style="color: #ff0000;">05ebab275936e94ca69d576c67bc8f8d </span>
  
at com.ibm.mm.server.persistence.rdbms.dao.ibatis.AccountDaoSqlMap.
  
getAccountByExternalId(AccountDaoSqlMap.java:55)
  
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)

You should open a PMR with IBM so that they can provide you with the fix that will prevent duplicate entries from being created in this table, and thus, preventing some users from logging in. Only users that have a duplicate row in the table will not be able to login. So, some users may still be able to login to Business Space.

There is a table called ACCOUNT, most likely in your Monitor database, unless you created a separate database for your Business Space.  Retrieve all the rows in this table and sort by EXTERNAL_ID ascending order.

<a href="http://www.sethgagnon.com/business-space-wont-let-me-login-to-view-business-monitor-dashboards/account-table/" rel="attachment wp-att-991"><img class="alignnone size-full wp-image-991" alt="ACCOUNT table" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/12/ACCOUNT-table.png?resize=900%2C558" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/12/ACCOUNT-table.png?w=1012 1012w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/12/ACCOUNT-table.png?resize=300%2C185 300w" sizes="(max-width: 900px) 100vw, 900px" data-recalc-dims="1" /></a>

Simply look for the ID that is mentioned in the error in you SystemOut.log for Business Space (as seen in red above). You will see two rows there in your table. Delete one of the rows and Commit your changes.

After you restart your Business Space server, you will be able to log in to Business Space again.