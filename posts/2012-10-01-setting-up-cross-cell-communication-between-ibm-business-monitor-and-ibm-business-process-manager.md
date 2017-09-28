---
title: Setting Up Cross Cell Communication Between IBM Business Monitor and IBM Business Process Manager
author: Seth
type: post
date: 2012-10-01T12:29:49+00:00
url: /setting-up-cross-cell-communication-between-ibm-business-monitor-and-ibm-business-process-manager/
networkpub_twitterhash:
  - BPM
networkpub_ogtype_facebook:
  - article
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor

---
<span style="color: #000000;">The following describes how to configure cross cell communication between IBM Business Monitor and IBM Business Process Manager when the products are installed into separate cells. </span>

<span style="color: #000000;">Before running through these steps, you should already have a successful installation completed of both Business Process Manager and Business Monitor. All cluster members should be able to start successfully in each of the cells before continuing with these steps. Some areas of pictures are blocked out for privacy reasons.</span>

<!--more-->

**<span style="text-decoration: underline;"><span style="color: #000000;">Cross SSL Setup</span></span>**

<span style="color: #000000;">Follow steps outlined here to enable SSL between Monitor and BPM cells. These steps will need to be completed on both the Monitor cell and the BPM cell.</span>

<a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fcfg_ssl.html" target="_blank">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fcfg_ssl.html</a>

&nbsp;

&nbsp;

[<img class="alignnone size-large wp-image-948" title="monitor1" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor1-1024x617.png?resize=600%2C361" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor1.png?resize=1024%2C617 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor1.png?resize=300%2C180 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor1.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][1]

<span style="color: #000000;">On the Monitor cell, provide the BPM server and secure port of the BPM.AppTarget. On the BPM cell, provide the Monitor server and the secure port of the Monitor.AppTarget. Click Retrieve Signer Information and then click OK. Repeat this for any DNS names as well.</span>

[<img class="alignnone  wp-image-949" title="monitor2" alt="" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor2-1024x617.png?resize=600%2C361" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor2.png?resize=1024%2C617 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor2.png?resize=300%2C180 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor2.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][2]

<span style="color: #000000;">Ensure that the Override inherited values box is not checked for all nodes.</span>

**<span style="text-decoration: underline;"><span style="color: #000000;">Enabling Identity Assertion</span></span>**

<span style="color: #000000;">Follow the steps outlined here for both cells:</span>

<a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fidentity_assertion.html" target="_blank">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fidentity_assertion.html</a>

&nbsp;

&nbsp;

[<img class="alignnone size-large wp-image-951" title="monitor3" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor3-1024x617.png?resize=600%2C361" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor3.png?resize=1024%2C617 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor3.png?resize=300%2C180 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor3.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][3]

<span style="color: #000000;">Ensure Use identity assertion is selected and the Trusted identities are set to *.</span>

[<img class="alignnone size-large wp-image-952" title="monitor4" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor4-1024x617.png?resize=600%2C361" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor4.png?resize=1024%2C617 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor4.png?resize=300%2C180 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor4.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][4]

<span style="color: #000000;">Ensure Use identity assertion is selected and Use server trusted identity is selected.</span>

**<span style="text-decoration: underline;"><span style="color: #000000;">Sharing LTPA keys between cells</span></span>**

<span style="color: #000000;">Follow the steps outlined here for both cells:</span>

<a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fltpa_cfg.html" target="_blank">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5m1/index.jsp?topic=%2Fcom.ibm.wbpm.mon.admin.doc%2Fsec%2Fltpa_cfg.html</a>

&nbsp;

&nbsp;

[<img class="alignnone size-large wp-image-953" title="monitor5" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor5-1024x617.png?resize=600%2C361" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor5.png?resize=1024%2C617 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor5.png?resize=300%2C180 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor5.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][5]

<span style="color: #000000;">Provide a password (can be anything you want) and export the keys from both cells.</span>

[<img class="alignnone size-large wp-image-954" title="monitor6" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor6-1024x618.png?resize=600%2C362" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor6.png?resize=1024%2C618 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor6.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor6.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][6]

<span style="color: #000000;">Provide the keys you exported from the BPM cell to the Monitor cell and Import. Likewise, provide the Monitor keys to the BPM cell and Import.</span>

Restart both Monitor and BPM cells.

**<span style="text-decoration: underline;"><span style="color: #000000;">Configure Table-Based Event Delivery</span></span>**

<span style="color: #000000;">To configure the BPM cell to use table-based delivery, follow the steps outlined here:</span>

<a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.mon.imuc.doc%2Finst%2Fcfg_qb_cross_cell.html" target="_blank">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.mon.imuc.doc%2Finst%2Fcfg_qb_cross_cell.html</a>

&nbsp;

&nbsp;

<span style="color: #000000;">Specifically,</span>

[<img class="alignnone size-large wp-image-956" title="monitor7" alt="" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor7-1024x584.png?resize=600%2C342" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor7.png?resize=1024%2C584 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor7.png?resize=300%2C171 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor7.png?w=1189 1189w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][7]

<span style="color: #000000;">You will need to first create an Authentication Alias called MONITOR and set the user name and password to the DB username and password for the Monitor database. </span>

<span style="color: #000000;">After the Auth Alias is created, you can edit the /ems_source/scripts/monitor/configureQueueByPass.py script for your Monitor environment. You will then run the following command on the BPM cell to configure the table-based events:</span>

<span style="color: #000000;">wsadmin.sh -lang jython -f &#8220;/ems_source/scripts/monitor/configureQueueBypass.py&#8221;</span>

[<img class="alignnone size-large wp-image-957" title="monitor8" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor8-1024x584.png?resize=600%2C342" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor8.png?resize=1024%2C584 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor8.png?resize=300%2C171 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor8.png?w=1189 1189w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][8]

<span style="color: #000000;">To verify, check under your JDBC datasources and look for MONITOR_<em>Cellname</em>_Routing_Database datasource</span>

**<span style="text-decoration: underline;"><span style="color: #000000;">Configure Queue-Based Event Delivery (for Lombardi)</span></span>**

<span style="color: #000000;">On the Monitor cell, you will need to perform the outlined steps here:</span>

<a href="http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.mon.imuc.doc%2Finst%2Fcfg_jms_cross_cell.html" target="_blank">http://publib.boulder.ibm.com/infocenter/dmndhelp/v7r5mx/index.jsp?topic=%2Fcom.ibm.wbpm.mon.imuc.doc%2Finst%2Fcfg_jms_cross_cell.html</a>

&nbsp;

<span style="color: #000000;">Specifically,</span>

<span style="color: #000000;">On the Monitor server, edit the properties file found in D:\IBM\WebSphere70\01\AppServer\scripts.wbm\crossCell\configureRemoteMonitorBus.props for the given environment you are working with.</span>

<span style="color: #000000;">Then open a command prompt and execute the following command from D:\IBM\WebSphere70\01\AppServer\scripts.wbm\crossCell:</span>

[<img class="alignnone size-full wp-image-958" title="monitor9" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor9.png?resize=668%2C331" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor9.png?w=668 668w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor9.png?resize=300%2C148 300w" sizes="(max-width: 668px) 100vw, 668px" data-recalc-dims="1" />][9]

<span style="color: #000000;">Here you are providing the property file you previously edited.</span>

<span style="color: #000000;">If asked to trust the ssl store, select yes:</span>

[<img class="alignnone size-full wp-image-959" title="monitor10" alt="" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor10.png?resize=668%2C331" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor10.png?w=668 668w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor10.png?resize=300%2C148 300w" sizes="(max-width: 668px) 100vw, 668px" data-recalc-dims="1" />][10]

<span style="color: #000000;">Ensure successful completion:</span>

[<img class="alignnone size-full wp-image-960" title="monitor11" alt="" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor11.png?resize=668%2C331" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor11.png?w=668 668w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor11.png?resize=300%2C148 300w" sizes="(max-width: 668px) 100vw, 668px" data-recalc-dims="1" />][11]

<span style="color: #000000;">In BPM cell, create an Authentication Alias called EventEmitterAlias (Any valid user id and password combination should do):</span>

[<img class="alignnone size-large wp-image-961" title="monitor12" alt="" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor12-1024x584.png?resize=600%2C342" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor12.png?resize=1024%2C584 1024w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor12.png?resize=300%2C171 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor12.png?w=1189 1189w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][12]

<span style="color: #000000;">Copy the following files from Business Monitor to BPM installations (preserving the directory structure below WAS_HOME):<br /> WAS_HOME/installableApps.wbm/EmitterServices.ear (here you will need to create the installableApps.wbm directory first)<br /> WAS_HOME/plugins/com.ibm.wbimonitor.admin.command.jar<br /> WAS_HOME/plugins/com.ibm.wbimonitor.restconfig.jar</span>

<span style="color: #000000;">Restart the entire BPM cell and Monitor cell before continuing.</span>

<span style="color: #000000;">Run the following commands on the BPM cell:</span>

<span style="color: #000000;">./wsadmin.sh –lang jython (when prompted, provide your username and password that you would log into the WAS console with)</span>

<span style="color: #000000;">AdminTask.wbmConfigureEventEmitterFactory([&#8220;-cluster&#8221;, &#8220;BPM.Support&#8221;]) </span>

<span style="color: #000000;">AdminTask.wbmDeployBPMEmitterService([&#8220;-cluster&#8221;, &#8220;BPM.Support&#8221;])</span>

<span style="color: #000000;">AdminConfig.save()</span>

&nbsp;

<span style="color: #000000;">Navigate to Service Integration > Common Event Infrastructure > Event Service > Map security roles to users or groups, change all Roles to use Special Subject of Everyone</span>

<span style="color: #000000;"> <a href="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor14.png"><img class="alignnone size-large wp-image-964" title="monitor14" alt="" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor14-1024x619.png?resize=600%2C362" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor14.png?resize=1024%2C619 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor14.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/09/monitor14.png?w=1280 1280w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" /></a></span>

<span style="color: #000000;">Restart the entire BPM cell.</span><span style="color: #000000;"> </span>

 [1]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor1.png
 [2]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor2.png
 [3]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor3.png
 [4]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor4.png
 [5]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor5.png
 [6]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor6.png
 [7]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor7.png
 [8]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor8.png
 [9]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor9.png
 [10]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor10.png
 [11]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor11.png
 [12]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/monitor12.png