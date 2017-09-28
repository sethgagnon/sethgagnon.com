---
title: ILOG JRules Decision Warehouse Needs Database
author: Seth
type: post
date: 2012-06-15T14:37:21+00:00
url: /ilog-jrules-decision-warehouse-needs-database/
jabber_published:
  - 1339771202
email_notification:
  - 1339771203
categories:
  - ILOG JRules
tags:
  - decision
  - DW
  - ilog
  - RES
  - rules
  - warehouse
  - websphere

---
Have you set up your ILOG Rule Execution Server environments to you file based persistence instead of database persistence? If so, you may notice some issues when you try to test your rulesets in Rule Team Server using your Excel spreadsheet.

When you try to test through Rule Team Server using a spreadsheet, it will look for traces in the ILOG JRules Decision Warehouse on the Rule Execution Server. What I have discovered is that the Decision Warehouse cannot use file based persistence. It needs to use a database to store the trace information.

For example, a good way to check this is to perform a search in the Decision Warehouse tab of the Rule execution Server. If you get a server 500 error, like below, chance are that you have not configured your Decision Warehouse database.

<img src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/decisionwarehouse.jpg?resize=900%2C502" alt="decisionwarehouse.jpg" data-recalc-dims="1" />

<img src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/06/zrclip_001n6302fe31.png?resize=764%2C301" alt="" data-recalc-dims="1" />

You will need to ensure that you are using your original RES ear file (as by default it is configured for a database and not file based persistence), and create the datasource and tables needed for Decision Warehouse. You will also need to ensure your Decision Validation Services ear is setup for database usage. See the URLs below as an example, but please be sure to follow instructions for the proper version of ILOG that you are running.

RES Setup:

[http://pic.dhe.ibm.com/infocenter/brjrules/v7r1/index.jsp?topic=%2Fcom.ibm.websphere.ilog.jrules.install.doc%2FContent%2FBusiness\_Rules%2FDocumentation%2F\_pubskel%2FJRules\_Application\_Servers%2Fps\_Installing\_JRules_IC36.html][1]

DVS Setup:

[http://pic.dhe.ibm.com/infocenter/brjrules/v7r1/index.jsp?topic=%2Fcom.ibm.websphere.ilog.jrules.install.doc%2FContent%2FBusiness\_Rules%2FDocumentation%2F\_pubskel%2FJRules\_Application\_Servers%2Fps\_Installing\_JRules_IC204.html][2]

 [1]: http://pic.dhe.ibm.com/infocenter/brjrules/v7r1/index.jsp?topic=/com.ibm.websphere.ilog.jrules.install.doc/Content/Business_Rules/Documentation/_pubskel/JRules_Application_Servers/ps_Installing_JRules_IC36.html
 [2]: http://pic.dhe.ibm.com/infocenter/brjrules/v7r1/index.jsp?topic=/com.ibm.websphere.ilog.jrules.install.doc/Content/Business_Rules/Documentation/_pubskel/JRules_Application_Servers/ps_Installing_JRules_IC204.html