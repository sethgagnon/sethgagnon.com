---
title: Seeing SIB/ME Errors After Deploying a Module with SCA References?
author: Seth
type: post
date: 2012-12-21T15:48:27+00:00
url: /seeing-sibme-errors-after-deploying-a-module-with-sca-references-in-it/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - BPM Application Issues
  - Business Process Manager
  - WebSphere Application Server
tags:
  - application server
  - BPM
  - business process manager
  - deploying sca
  - deployment
  - module
  - SCA
  - update
  - websphere

---
A &#8220;hot&#8221; deployment or update is an update to a running application on a running server and the changes are dynamically applied without the need for restarting your application server. If you try to perform a &#8220;hot&#8221; update to a module containing SCA references, you may find that the module does not function correctly after the deployment, as WESB and WPS ( also IBM Business Process Manager) cache references to EJB stubs pointing to modules registered by the SCA runtime.

<!--more-->

You may notice the following errors in your SystemOut.log where you application is installed:

SCA unable to establish connection to SIB/ME in 108 secs.

Internal Error. : org.omg.CORBA.OBJECT\_NOT\_EXIST: SERVANT\_NOT\_FOUND

If you notice these errors and your application module is not functioning properly unless you restart your application server, then you most likely will need to update your SCA Feature Pack. The most recent version of the SCA Feature Pack 1.0.1.15 will allow you to perform &#8220;hot&#8221; updates on modules that contain SCA references, eliminating the need to restart your application server.

You can check your current installed feature pack version my running the WAS\_INSTALL\_ROOT/bin/versionInfo -maintenancePackages command.

You should see something like the following:
  
Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.future4.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.future5.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.future6.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.hu.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.it.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.ja.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.ko.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.pl.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.pt.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.pt_BR.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.ru.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.zh.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   cim.lang.zh_TW.con.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               11/17/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   was.embed.common.FP70021
  
Description              Embedded Express 7.0.0.21
  
Build Date               12/14/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   was.server.common.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               12/14/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   was.thinclient.common.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               12/14/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   was.embed.FP70021
  
Description              Embedded Express 7.0.0.21
  
Build Date               12/14/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   was.server.FP70021
  
Description              WebSphere Application Server 7.0.0.21
  
Build Date               12/14/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   7.5.1.0-WS-BPMADVWESB-IFIC79666
  
Description              Service Deploy reports error CWZMU0062E when a Data Handler primitive configuration file is contained within a library project
  
Build Date               2011/11/16

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   1.0.1-WS-SCA-FP0000013
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.enablement.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.featurepack.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.swebui.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sdo.core.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sdo.core.nd.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   1.0.0-WS-XML-FP0000011
  
Description              XML Feature Pack FixPack 1.0.0.11
  
Build Date               11/30/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.xml.enablement.FP10011
  
Description              XML Feature Pack FixPack 1.0.0.11
  
Build Date               11/30/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.xml.featurepack.FP10011
  
Description              XML Feature Pack FixPack 1.0.0.11
  
Build Date               11/30/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.xml.featurepack.nd.FP10011
  
Description              XML Feature Pack FixPack 1.0.0.11
  
Build Date               11/30/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.featurepack.nd.FP10113
  
Description              SCA Feature Pack FixPack 1.0.1.13
  
Build Date               12/05/2011

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   7.5.1.0-WS-BPMADVWESB-IFJR41785
  
Description              Store and Forward throws a null pointer exception in a cluster.
  
Build Date               2012/02/10

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   1.0.1-WS-SCA-FP0000015
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.enablement.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.featurepack.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.swebui.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sdo.core.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sdo.core.nd.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

Installed Maintenance Package
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
Maintenance Package ID   fep.sca.featurepack.nd.FP10115
  
Description              SCA Feature Pack FixPack 1.0.1.15
  
Build Date               08/14/2012

&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;
  
End Installation Status Report
  
&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8211;

&nbsp;

You can find complete details on the latest SCA Feature Pack 1.0.1.15 here:

<http://www-01.ibm.com/support/docview.wss?uid=swg24033273>