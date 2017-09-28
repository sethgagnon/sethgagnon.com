---
title: The Importance of Unique Cell Names in BPM 7.5
author: Seth
type: post
date: 2012-04-05T23:40:00+00:00
url: /the-importance-of-unique-cell-names-in-bpm-7-5/
blogger_blog:
  - www.sethgagnon.com
blogger_author:
  - Seth Gagnon
blogger_3e80d94236879be645dcffcd98a21f45_permalink:
  - 7596598826871314922
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190156512109412353";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150782164774919";}}}'
categories:
  - BPM Infrastructure Issues
  - Business Process Manager
tags:
  - BPM
  - business process manager
  - IBM BPM
  - websphere

---
<div class="post-header-line-1">
   In order for the many features of IBM Business Process Manager (BPM) Advanced 7.5 product to function as designed, one must plan accordingly and pay attention to detail, specifically around naming conventions.<br /> BPM 7.5 includes a feature known as the Process Inspector. This feature, in Process Designer, allows developers to run and debug processes in the Process Center authoring environment, as well as, remote Process Server environments that are connected to the Process Center. Process Inspector provides a centralized location for viewing and debugging running process instances in any environment connected to your Process Center. Table 1 below outlines some of the main tasks that the Inspector allows a developer to perform.
</div>

<div class="post-body entry-content">
  <div class="separator" style="clear: both; text-align: center;">
    <a style="margin-left: 1em; margin-right: 1em;" href="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell11.jpg"><img src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell11.jpg?resize=320%2C209" alt="" border="0" data-recalc-dims="1" /></a>
  </div>
  
  <p>
    <strong>Table 1 – Tasks in Process Inspector (IBM, 2011)</strong>
  </p>
  
  <p>
    <!--more-->
  </p>
  
  <p>
    In order to use the Inspector functionality to its full potential, it is important to ensure that each of your BPM cells has unique names. According to the IBM BPM 7.5 InfoCenter,
  </p>
  
  <blockquote class="tr_bq">
    <p>
      “Use a unique name for the deployment manager cell. A cell name must be unique in any circumstance in which the product is running on the same physical workstation or cluster of workstations, such as a Sysplex. Additionally, a cell name must be unique in any circumstance in which network connectivity between entities is required either between the cells or from a client that must communicate with each of the cells. Cell names also must be unique if their name spaces are going to be federated. Otherwise, you might encounter symptoms such as a javax.naming.Name NotFoundException exception, in which case, you need to create uniquely named cells.” (IBM, 2011)
    </p>
  </blockquote>
  
  <p>
    Process Inspector does make use of connectivity between the cells and also from a client that must communicate with each of the cells. When connecting to Process Center through the Inspector, there is cross-cell communication that occurs when Inspector goes to look for the running instances you have in one of your remote Process Server environments. As an example, if a developer has deployed code onto the Process Center server (also known as the playback server) and is now ready to test the code on a remote Process Server environment, Process Inspector will allow the developer to kick off a process instance and debug the code step by step through the process, provided the snapshot has already been deployed to the remote Process Server. The drop down box in Figure 1 shows the various Process Server environments that are connected to the Process Center.
  </p>
  
  <div class="separator" style="clear: both; text-align: center;">
    <a style="margin-left: 1em; margin-right: 1em;" href="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell21.jpg"><img src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell21.jpg?resize=320%2C193" alt="" border="0" data-recalc-dims="1" /></a>
  </div>
  
  <p>
    <strong>Figure 1 – View of Process Inspector while running a process instance</strong>
  </p>
  
  <p>
    Normally, after selecting an environment to test your process instance on, Inspector would connect to the remote Process Server and allow you to execute your tests. However, if your BPM cells for all of your environments are named with the exact same name, you may see a screen resembling Figure 2, even though you have already successfully deployed the snapshot.
  </p>
  
  <div class="separator" style="clear: both; text-align: center;">
    <a style="margin-left: 1em; margin-right: 1em;" href="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell31.jpg"><img src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/04/bpm_cell31.jpg?resize=320%2C109" alt="" border="0" data-recalc-dims="1" /></a>
  </div>
  
  <p>
    <strong>Figure 2 – Error messaging indicating no snapshots are deployed</strong>
  </p>
  
  <p>
    When the BPM cell names are all the same, cross-cell communication experiences issues that will cause you to lose key functionality of the products, as described above. Figure 3 provides a high level view (as an example) of the connectivity between Process Designer (which contains Process Inspector), Process Center, and Process Server environments:
  </p>
  
  <div class="separator" style="clear: both; text-align: center;">
    <a style="margin-left: 1em; margin-right: 1em;" href="http://sethgagnon.files.wordpress.com/2012/04/bpm_cell41.jpg"><img src="http://sethgagnon.files.wordpress.com/2012/04/bpm_cell41.jpg?w=300&#038;resize=320%2C268" alt="" border="0" data-recalc-dims="1" /></a>
  </div>
  
  <p>
    <strong>Figure 3 – Cross Cell Communication for Deployment in BPM 7.5 (Markowitz, 2011)</strong>
  </p>
  
  <p>
    In conclusion, it is imperative that you review the pre-requisites for installing IBM BPM 7.5 Advanced, or any products for that matter, thoroughly to ensure a successful implementation. The old saying “measure twice and cut once” is always a good rule of thumb to avoid rework and further expense down the road.
  </p>
  
  <p>
    <strong>Works Cited:</strong><br /> IBM. (2011). Naming considerations for profiles, nodes, servers, hosts, and cells. Retrieved February 16, 2012, from IBM Business Process Manager 7.5 InfoCenter: <a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.main.doc%2Ftopics%2Fcins_naming.html"><span style="color: black;">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.main.doc%2Ftopics%2Fcins_naming.html</span></a><br /> IBM. (2011). Running and debugging processes with the Inspector. Retrieved February 16, 2012, from IBM Business Process Manager 7.5 InfoCenter: <a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.wle.editor.doc%2Ftopics%2Frunning_debugging_procs.html"><span style="color: black;">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.wle.editor.doc%2Ftopics%2Frunning_debugging_procs.html</span></a><br /> Markowitz, E. (2011, 11). Product Development Director at Prolifics.
  </p>
</div>

<div class="blogger-post-footer">
  <img src="https://blogger.googleusercontent.com/tracker/7034800122336943439-7596598826871314922?l=www.sethgagnon.com" alt="" width="1" height="1" />
</div>