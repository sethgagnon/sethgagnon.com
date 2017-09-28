---
title: How to Delete Process Applications from IBM BPM 7.5.1
author: Seth
type: post
date: 2012-04-05T23:38:00+00:00
url: /how-to-delete-process-applications-from-ibm-bpm-7-5-1/
blogger_blog:
  - www.sethgagnon.com
blogger_author:
  - Seth Gagnon
blogger_3e80d94236879be645dcffcd98a21f45_permalink:
  - 7560208446721502407
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190156692472872962";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150782166554919";}}}'
categories:
  - "BPM Product How To's"
  - Business Process Manager
tags:
  - BPM
  - business process manager
  - IBM BPM
  - process application
  - websphere

---
<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">As a new feature of the Business Process Manager V7.5.1 platform, process applications can now be deleted from the repository.  In the previous version of BPM, version 7.5.0 & 7.5.0.1, users could only archive snapshots within a process application.  This did not remove the application; rather it was merely hidden from the default view and it was still stored in the repository and the database.</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">In the latest version of BPM, users can now actually delete the process application, and in turn, delete all snapshots and instances tied to that application, including deletion of these entries from the database.</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">To delete a process application, click on the process application that you want to delete and then click on Manage.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp11.png"><img src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp11.png?resize=320%2C192" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <!--more-->
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Next, click on Archive Process App and click on Archive.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="http://sethgagnon.files.wordpress.com/2012/04/processapp21.png"><img src="http://sethgagnon.files.wordpress.com/2012/04/processapp21.png?w=300&#038;resize=320%2C192" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Click on the Process Apps tab of Process Center and then click on Archived.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp31.png"><img src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp31.png?resize=320%2C192" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Click on the process app that you previously archived and select Delete Process App, click on Delete.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="http://sethgagnon.files.wordpress.com/2012/04/processapp41.png"><img src="http://sethgagnon.files.wordpress.com/2012/04/processapp41.png?w=300&#038;resize=320%2C192" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">If you then return to the Process Apps tab in Process center, you will notice that the process app no longer appears in the list.</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">We can actually confirm that all database entries are also removed as part of the process app deletion. Here we can see that the entry for our application named TestApplication was added to the BPMDB in the table LSW_PROJECT.</span>
</div>

<div class="separator" style="clear: both; text-align: center;">
  <a style="margin-left: 1em; margin-right: 1em;" href="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp51.png"><img src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/processapp51.png?resize=320%2C252" alt="" border="0" data-recalc-dims="1" /></a>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
   
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">After deleting the process app, this entry is no longer present in the table.  If the application contained snapshots and BPDs, these entries would also be removed from the LSW_SNAPSHOT and LSW_BPD tables respectively.</span>
</div>

<div class="MsoNormal" style="margin: 0 0 10pt;">
  <span style="font-family: Calibri;">Please keep in mind, that this cleanup only happens in Process Center. Currently, the product does not have the capaibility to clean up these components on the Process Server side. However, this is an important new feature to help keep your Process Center repository clean and its database clean and efficient.</span>
</div>

<div class="blogger-post-footer">
  <img src="https://blogger.googleusercontent.com/tracker/7034800122336943439-7560208446721502407?l=www.sethgagnon.com" alt="" width="1" height="1" />
</div>