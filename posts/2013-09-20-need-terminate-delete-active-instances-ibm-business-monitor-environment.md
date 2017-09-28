---
title: Do you need to terminate and delete active instances in your IBM Business Monitor environment?
author: Seth
type: post
date: 2013-09-20T16:02:41+00:00
url: /need-terminate-delete-active-instances-ibm-business-monitor-environment/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor

---
There are occasional situations where you may need to terminate and delete active monitoring context instances against a given IBM Business Monitor model. If this situation were to arise, here is an <span style="text-decoration: underline;"><strong>unsupported</strong> </span>method to try from IBM:

<span style="text-decoration: underline;"><strong> Please note that this method is stated as-is. You cannot open a PMR requesting support on using this approach. You can try this at your own risk! I can say that I have used this method myself and it did work for me.</strong></span>

Abstract

You may need to manually terminate open monitoring context instances.

Resolution

There may be situations where open monitoring contexts need to be manually terminated, due to a variety of reasons. The procedure described in this technote can be used to terminate contexts should the need arise. Note that this procedure is not officially supported and is provided &#8220;as-is&#8221;.

Determine which monitoring context instances to terminate by examining database tables in the monitor model schema (which is named similarly to the monitor model). If Data Movement Services is not enabled, then the table name for a monitoring context begins with &#8220;MCT&#8221; and is followed by a monitoring context identifier and the model version date and time stamp. If Data Movement Services is enabled, then examine table names beginning with &#8220;TGT&#8221; rather than &#8220;MCT&#8221;. (The remainder of this technote will mention &#8220;MCT&#8221; only. If Data Movement Services is enabled, this is actually referring to the &#8220;TGT&#8221; tables instead.)

If there is a monitoring context hierarchy with a parent monitoring context and child monitoring contexts, then begin by examining the table for the parent monitoring context. Note that if the PARENT_MCIID column in an MCT table does not have any values, then this monitoring context is a parent monitoring context or the monitor model does not have a monitoring context hierarchy. Referring to the monitor model definition will also be helpful during this process.

Make a list of MCIID values for rows where the READY\_FOR\_DELETE column equals zero and the key metric column (or any other metric or combination of metrics) matches the criteria you determine for terminating open contexts. (You may be able to create an SQL SELECT statement to query the table for these rows.) If the monitor model has parent and child monitoring contexts, follow step 3 for each child monitoring context MCT table. Match MCIID values noted in step 1 against the PARENT\_MCIID column in the child monitoring context to determine which rows for the child monitoring context are candidates for termination. If there are not parent and child monitoring contexts, then follow step 3 for the MCIID rows identified in step 1. Update the following columns in each row of the MCT table or tables identified. (You may be able to create a single SQL UPDATE statement that selects rows based on the SELECT statement mentioned in step 1.) Set the AB\_TERMINATION\_TIME column to the current date. Set the TERMINATION\_TIME column to the current date and time. Set the READY\_FOR\_DELETE column to &#8216;1&#8217;. If the monitor model contains stopwatches, then there will be columns that start with &#8216;T&#8217;. If a column starting with &#8220;T1&#8221; has a value other than &#8220;0001-01-01 00:00:00&#8221; (if the value is different, then the stopwatch is running), then information on the accumulated duration of the stopwatch needs to be added to the column starting with &#8220;T2&#8221;. Subtract the value of the &#8220;T1&#8221; column from the current time to obtain a duration, and then add this duration to the current value in the &#8220;T2&#8221; column. If the monitor model has a parent monitoring context, then follow step 3 for all of the MCIID rows identified in step 1 for the parent monitoring context MCT table.

Below are examples of SQL statements that terminate monitoring contexts that have been open for at least 30 days:

DB2:

UPDATE MYMM.MCT\_MYMMMC.20110101120000 SET AB\_TERMINATION\_TIME = CURRENT DATE, TERMINATION\_TIME = CURRENT TIMESTAMP, READY\_FOR\_DELETE = 1 WHERE CURRENT DATE &#8211; AB\_CREATION\_TIME >= 30 [steps 3.a. through 3.c.] UPDATE MYMM.MCT\_MYMMMC.20110101120000 SET T2\_MYSTOPWATCH = T2\_MYSTOPWATCH + (CURRENT TIMESTAMP &#8211; T1\_MYSTOPWATCH) WHERE CURRENT DATE &#8211; AB\_CREATION\_TIME >= 30 AND T1\_MYSTOPWATCH <> TIMESTAMP\_FORMAT(&#8216;0001-01-01 00:00:00&#8242;,&#8217;YYYY-MM-DD HH24:MI:SS&#8217;) [step 3.d.]

Oracle:

UPDATE MYMM.MCT\_MYMMMC.20110101120000 SET AB\_TERMINATION\_TIME = SYSDATE, TERMINATION\_TIME = SYSTIMESTAMP, READY\_FOR\_DELETE = 1 WHERE SYSDATE &#8211; AB\_CREATION\_TIME >= 30 [steps 3.a. through 3.c.] UPDATE MYMM.MCT\_MYMMMC.20110101120000 SET T2\_MYSTOPWATCH = T2\_MYSTOPWATCH + (SYSTIMESTAMP &#8211; T1\_MYSTOPWATCH) WHERE SYSDATE &#8211; AB\_CREATION\_TIME >= 30 AND T1\_MYSTOPWATCH <> TO\_TIMESTAMP(&#8216;0001-01-01 00:00:00&#8242;,&#8217;YYYY-MM-DD HH24:MI:SS&#8217;) [step 3.d.]

If you only have a few running instances that you want to delete, you can also delete the rows from the MCT tables mentioned above.