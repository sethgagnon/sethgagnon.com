---
title: Common Post Installation Steps for IBM BPM Advanced
author: Seth
type: post
date: 2012-06-27T18:07:16+00:00
url: /common-post-installation-steps-ibm-bpm-advanced/
categories:
  - "BPM Product How To's"
  - Business Process Manager
tags:
  - BPM
  - BPM 7.5
  - bpm installation
  - business process manager
  - IBM
  - IBM BPM
  - websphere

---
Installing IBM BPM 7.5.x is a fairly straight forward process.  However, the post installation configuration steps can be the most time-consuming portion of the installation. Below is a brief list of some of the common post installation configuration steps that need should be completed. Please keep in mind that this list is only outlining some of the common configuration steps that are needed, specific to BPM. I am assuming things like enabling security, etc are already completed. Obviously, your environment may be slightly different and some of these steps may not apply. So, feel free to use this list to get you thinking and ensure you haven&#8217;t missed anything.

## Common BPM Configuration Steps

  1. Human Task Manger
  2. REST services
  3. Configure SMTP Server
  4. Change Default password for internal users (except tw_user)
  5. Configure Deployment Groups
  6. Process Center &#8211; Debug Role
  7. Update 100Custom.xml
  8. Update  99Local.xml
  9. Change JVM heap size
 10. Change transaction logs location and compensation  logs location
 11. Change core dump folder
 12. Messaging Engine priority setting
 13. Adjust Process Center and Process Server urls to accommodate web servers (if applicable)
 14. Enable monitoring of environments

Also feel free to check out the BPM info center for some additional advanced configuration steps:

[http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.imuc.ebpm.doc%2Ftopics%2Fcpost\_cnfg\_oview.html][1]

 [1]: http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.imuc.ebpm.doc%2Ftopics%2Fcpost_cnfg_oview.html