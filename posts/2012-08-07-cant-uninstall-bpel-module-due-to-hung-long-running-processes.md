---
title: Can’t Uninstall BPEL Module Due to Hung Long Running Processes?
author: Seth
type: post
date: 2012-08-07T19:36:22+00:00
url: /cant-uninstall-bpel-module-due-to-hung-long-running-processes/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Process Manager
  - General IBM

---
In order to uninstall a BPEL module from a WebSphere Process Server or Business Process Manager environment, there can not be any running long running processes against that module. If you try to uninstall the BPEL module with running instances, you may see the error below in your SystemOut.log:

[8/7/12 15:22:47:100 EDT] 00000085 ProcessApplic I   CWWBF0025E: Process **_PROCESSNAME_** of application _**APPLICATIONNAME**_ still has instances. Terminate and delete all process instances before updating or uninstalling a process application.

<!--more-->

Where _**PROCESSNAME**_ is the name of the running process template and _**APPLICATIONNAME**_ is the name of the deployed module.

If you find that you cannot terminate these instances in Business Process Choreographer Explorer and they are hung or in a &#8220;zombie&#8221; state, you can execute a script that will delete these running instances and force the uninstallation of the module. This has certainly come in handy for me quite a few times.  Here is the script:

./wsadmin.sh -lang jacl -f _**WAS\_INSTALL\_ROOT**_/ProcessChoreographer/admin/bpcTemplates.jacl -uninstall _**APPLICATIONNAME**_ -force

Where _**WAS\_INSTALL\_ROOT** _is the installation path of your WebSphere environment (i.e. /opt/IBM/WebSphere/AppServer/) and _**A****PPLICATIONNAME**_ is the name of the module you want to uninstall.

Again, this will delete all instances against that module and uninstall the modulem (ear file). You will then be able to deploy your new version of code.