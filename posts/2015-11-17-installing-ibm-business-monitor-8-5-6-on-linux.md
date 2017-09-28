---
title: Installing IBM Business Monitor 8.5.6 on Linux
author: Seth
type: post
date: 2015-11-17T20:06:06+00:00
url: /installing-ibm-business-monitor-8-5-6-on-linux/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - Business Monitor
tags:
  - business monitor
  - business space
  - IBM BPM
  - IBM Business Monitor
  - websphere

---
<div class="clarify-article-content">
  <div class="clarify-article-description">
    <p>
      This document outlines the installation procedures for the IBM Business Monitor 8.5.6 product for a development environment.
    </p>
  </div>
</div>

<!--more-->

<div class="clarify-article-content">
  <div class="clarify-steps-container">
    <div id="clarify-step-1" class="clarify-step-container">
      <h3 class="clarify-step-title">
        1. A Development Environment
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          The following outlines the installation steps for the DEV environment.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-2" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.1 Installation of Binaries for DEV
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              This section describes the steps to install the bianries for Business Monitor.
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-3" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.2 Environment Setup
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Please ensure that you have prepped your operating system using the following instructions:
            </p>
            
            <p>
              <a href="http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.6/com.ibm.wbpm.mon.imuc.doc/topics/prep_bpm_os_lin.html?lang=en">http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.6/com.ibm.wbpm.mon.imuc.doc/topics/prep_bpm_os_lin.html?lang=en</a>
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-4" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.3 Extract the binaries to a common location
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              The directory structure should look like that in the following image.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/extract-the-binaries-to-a-common-location.png?resize=813%2C533" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-5" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.4 Install the Business Monitor Binaries
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              There are a few different ways to install the product binaries: 1) Using the Launchpad, which requires your servers to have a working web browser and be able to export your display, or 2) Using response files to install the product binaries. We will be using option 2.
            </p>
            
            <p>
              &nbsp;
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-6" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.5 Prep your response file
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Our response file has been created and contains all the information necessary to install the product binaries for IBM Business Monitor (non-production). We will have another response file for production. Here is the text of the response file:
            </p>
            
            <p>
              <?xml version=&#8217;1.0&#8242; encoding=&#8217;UTF-8&#8242;?>
            </p>
            
            <p>
              <agent-input>
            </p>
            
            <p>
              <variables>
            </p>
            
            <p>
              <variable name=&#8217;sharedLocation&#8217; value=&#8217;<span style="color: #ff0000;">/opt/IBM/IMShared</span>&#8216;/>
            </p>
            
            <p>
              </variables>
            </p>
            
            <p>
              <server>
            </p>
            
            <p>
              <repository location=&#8217;<span style="color: #ff0000;">/was_inst_BAM_V856/ExtractedBinaries/repository</span>&#8216;/>
            </p>
            
            <p>
              </server>
            </p>
            
            <p>
              <profile id=&#8217;IBM WebSphere Application Server V8.5&#8242; installLocation=&#8217;<span style="color: #ff0000;">/opt/IBM/WebSphere/AppServer</span>&#8216;>
            </p>
            
            <p>
              <data key=&#8217;eclipseLocation&#8217; value=&#8217;<span style="color: #ff0000;">/opt/IBM/WebSphere/AppServer</span>&#8216;/>
            </p>
            
            <p>
              <data key=&#8217;user.import.profile&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <data key=&#8217;cic.selector.os&#8217; value=&#8217;linux&#8217;/>
            </p>
            
            <p>
              <data key=&#8217;cic.selector.arch&#8217; value=&#8217;x86&#8217;/>
            </p>
            
            <p>
              <data key=&#8217;cic.selector.ws&#8217; value=&#8217;gtk&#8217;/>
            </p>
            
            <p>
              <data key=&#8217;cic.selector.nl&#8217; value=&#8217;en&#8217;/>
            </p>
            
            <p>
              </profile>
            </p>
            
            <p>
              <install modify=&#8217;false&#8217;>
            </p>
            
            <p>
              <!&#8211; 8.5.0.0-WS-WASJavaSDK-LinuxX64-IFPI35615 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;8.5.0.0-WS-WASJavaSDK-LinuxX64-IFPI35615&#8217;/>
            </p>
            
            <p>
              <!&#8211; 8.5.5.5-WS-WAS-IFPI35502 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;8.5.5.5-WS-WAS-IFPI35502&#8217;/>
            </p>
            
            <p>
              <!&#8211; 8.5.5.5-WS-WASProd-IFPI35667 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;8.5.5.5-WS-WASProd-IFPI35667&#8217;/>
            </p>
            
            <p>
              <!&#8211; IBM WebSphere Application Server Network Deployment 8.5.5.5 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;com.ibm.websphere.ND.v85&#8242; version=&#8217;8.5.5005.20150220_0158&#8242; features=&#8217;core.feature,ejbdeploy,thinclient,embeddablecontainer,com.ibm.sdk.6_64bit&#8217; installFixes=&#8217;none&#8217;/>
            </p>
            
            <p>
              <!&#8211; IBM WebSphere SDK Java Technology Edition (Optional) 7.0.8.10 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;com.ibm.websphere.IBMJAVA.v70&#8242; version=&#8217;7.0.8010.20150219_1802&#8242; features=&#8217;com.ibm.sdk.7&#8242; installFixes=&#8217;none&#8217;/>
            </p>
            
            <p>
              <!&#8211; IBM® Business Monitor 8.5.6.0 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;com.ibm.websphere.MON.v85&#8242; version=&#8217;8.5.6000.20150303_1517&#8242; features=&#8217;<span style="color: #ff0000;">Monitor.NonProduction</span>&#8216; installFixes=&#8217;none&#8217;/>
            </p>
            
            <p>
              <!&#8211; IBM® Cognos Business Intelligence 64 bit 10.2.2.0 &#8211;>
            </p>
            
            <p>
              <offering profile=&#8217;IBM WebSphere Application Server V8.5&#8242; id=&#8217;com.ibm.ws.cognos.v1022.linuxia64&#8242; version=&#8217;10.2.2.20150304_1653&#8242; features=&#8217;com.ibm.cognos.feature&#8217; installFixes=&#8217;none&#8217;/>
            </p>
            
            <p>
              </install>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.eclipseCache&#8217; value=&#8217;${sharedLocation}&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.connectTimeout&#8217; value=&#8217;30&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.readTimeout&#8217; value=&#8217;45&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.downloadAutoRetryCount&#8217; value=&#8217;0&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;offering.service.repositories.areUsed&#8217; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.ssl.nonsecureMode&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.http.disablePreemptiveAuthentication&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;http.ntlm.auth.kind&#8217; value=&#8217;NTLM&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;http.ntlm.auth.enableIntegrated.win32&#8242; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.preserveDownloadedArtifacts&#8217; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.keepFetchedFiles&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;PassportAdvantageIsEnabled&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.core.preferences.searchForUpdates&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.agent.ui.displayInternalVersion&#8217; value=&#8217;false&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.sharedUI.showErrorLog&#8217; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.sharedUI.showWarningLog&#8217; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              <preference name=&#8217;com.ibm.cic.common.sharedUI.showNoteLog&#8217; value=&#8217;true&#8217;/>
            </p>
            
            <p>
              </agent-input>
            </p>
            
            <p>
              This will install the product to /opt/IBM/WebSphere/AppServer. Notice some of the areas highlighted in red to observe installation paths and features. This will not install DB2 Express, as we are using Oracle for our product database.
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-7" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.6 Run the command to install the binaries using your response file.
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Make sure you are in the following directory: /was_inst/BPM_856/ExtractedBinaries/IM64/
            </p>
            
            <p>
              Execute the following command:
            </p>
            
            <p>
              /was_inst/BAM_V856/ExtractedBinaries/IM64/installc -acceptLicense input /was_inst/BAM_V856/ExtractedBinaries/MonNonProdResponseFile.xml -log /was_inst/BAM_V856/ExtractedBinaries/installLogs/silent_install.log
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/run-the-command-to-install-the-binaries-using-your-response-file.png?resize=813%2C145" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-8" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.7 Verify binary installation
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Go to /opt/IBM/WebSphere/AppServer/bin and execute the following command:
            </p>
            
            <p>
              ./versionInfo.sh
            </p>
            
            <p>
              You should see the following in the image below.
            </p>
            
            <p>
              <strong>Please note you will need to repeat these steps 1.1 &#8211; 1.6 for each Linux server that will be part of your clustered environment!</strong>
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/verify-binary-installation.png?resize=639%2C749" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-9" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.8 Creation of Deployment Manager Profile in Dev
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              To create the Deployment Manager profile, you will need to execute the following command from /opt/IBM/WebSphere/AppServer/bin
            </p>
            
            <p>
              ./manageprofiles.sh -create -templatePath &#8220;/opt/IBM/WebSphere/AppServer/profileTemplates/wbmonitor/dmgr&#8221; -profileName Dmgr01 -profilePath &#8220;/opt/IBM/WebSphere/AppServer/profiles/Dmgr01&#8221; -cellName MonCell1 -nodeName DMGRNode -enableAdminSecurity true -adminUserName wsadmin -adminPassword ADMINPASSWORD -wbmDBType Oracle11g -wbmDBDelayConfig true  -wbmDBSchemaName MONITOR -wbmDBName ibmdtool -wbmDBUserId Monitor -wbmDBPassword DBPASSWORD -wbmDBJDBCClasspath &#8220;/opt/IBM/WebSphere/AppServer/jdbcdrivers/Oracle&#8221; -wbmDBHostName DBHOSTNAME -wbmDBServerPort 1521 -wbmDBDriverType 4 -wbmCognosDBName ibmdtool -wbmCognosDBUserName COGNOS -wbmCognosDBPassword DBPASSWORD
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              The output is seen here
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/creation-of-deployment-manager-profile-in-dev.png?resize=813%2C187" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-10" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.9 Creation of Custom Node Profile in Dev
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              To create the Node profile, you will need to execute the following command from /opt/IBM/WebSphere/AppServer/bin
            </p>
            
            <p>
              ./manageprofiles.sh -create -templatePath &#8220;/opt/IBM/WebSphere/AppServer/profileTemplates/wbmonitor/managed&#8221; -profileName MonServer01 -profilePath &#8220;/opt/IBM/WebSphere/AppServer/profiles/MonServer01&#8221; -nodeName Node -federateLater false -dmgrAdminUserName wsadmin -dmgrAdminPassword ADMINPASSWORD -dmgrHost HOSTNAME -dmgrPort 8879 -wbmDBType Oracle11g -wbmDBJDBCClasspath &#8220;/opt/IBM/WebSphere/AppServer/jdbcdrivers/Oracle&#8221;
            </p>
            
            <p>
              The output is seen in the second image.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/creation-of-custom-node-profile-in-dev.png?resize=813%2C151" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-11" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.10 Creation of Deployment Environment in Dev
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              The following steps outline how to create the Monitor Deployment Environment in DEV.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              BEFORE CONTINUING, PLEASE ENSURE STEP 2 HAS BEEN COMPLETED.
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-12" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.11 Prep properties file
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Below is a copy of the properties file needed to create clusters on one Node and single member clusters:
            </p>
            
            <p>
              # The IBM Business Monitor Golden Topology is a three cluster environment
            </p>
            
            <p>
              # where each cluster has one member.
            </p>
            
            <p>
              clusterName.1=MonAppCluster
            </p>
            
            <p>
              clusterName.1.capabilities=application
            </p>
            
            <p>
              clusterName.1.memberName.1=MonAppServer01
            </p>
            
            <p>
              clusterName.1.memberName.1.memberNode.1=Node
            </p>
            
            <p>
              clusterName.2=MonMECluster
            </p>
            
            <p>
              clusterName.2.capabilities=messaging
            </p>
            
            <p>
              clusterName.2.memberName.1=MonMEServer01
            </p>
            
            <p>
              clusterName.2.memberName.1.memberNode.1=Node
            </p>
            
            <p>
              clusterName.3=MonSupCluster
            </p>
            
            <p>
              clusterName.3.capabilities=support
            </p>
            
            <p>
              clusterName.3.memberName.1=MonSupServer01
            </p>
            
            <p>
              clusterName.3.memberName.1.memberNode.1=Node
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-13" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.12 Run deployment environment creation
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              Run the following script from /opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig
            </p>
            
            <p>
              ./monConfig.sh -d Dmgr01 -u wsadmin -p ADMINPASSWORD -c /opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/customized_monconfig.properties
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2015/11/run-deployment-environment-creation.png?resize=813%2C45" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-14" class="clarify-sub-step-container">
          <h4 class="clarify-step-title">
            1.13 Output from deployment environment creation
          </h4>
          
          <div class="clarify-step-instructions">
            <p>
              WAS_HOME = /opt/IBM/WebSphere/AppServer
            </p>
            
            <p>
              THIS_CLASSPATH = /opt/IBM/WebSphere/AppServer/lib/wbminstall_util.jar:/opt/IBM/WebSphere/AppServer/lib/wbminstall_log.jar:/opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/lib/JSON4J.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.spi.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.repository.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.bpm.config.jar:/opt/IBM/WebSphere/AppServer/runtimes/com.ibm.ws.ejb.thinclient_8.5.0.jar
            </p>
            
            <p>
              /opt/IBM/WebSphere/AppServer/bin/wsadmin.sh  -profileName Dmgr01 -conntype SOAP -username wsadmin -password ADMINPASSWORD -lang jython -wsadmin_classpath /opt/IBM/WebSphere/AppServer/lib/wbminstall_util.jar:/opt/IBM/WebSphere/AppServer/lib/wbminstall_log.jar:/opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/lib/JSON4J.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.spi.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.repository.jar:/opt/IBM/WebSphere/AppServer/plugins/com.ibm.bpm.config.jar:/opt/IBM/WebSphere/AppServer/runtimes/com.ibm.ws.ejb.thinclient_8.5.0.jar -f /opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/monConfig.jy /opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/customized_monconfig.properties
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/lib/JSON4J.jar&#8217;
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.jar&#8217;
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.lifecycle.spi.jar&#8217;
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/plugins/com.ibm.wbimonitor.repository.jar&#8217;
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/plugins/com.ibm.bpm.config.jar&#8217;
            </p>
            
            <p>
              *sys-package-mgr*: processing new jar, &#8216;/opt/IBM/WebSphere/AppServer/runtimes/com.ibm.ws.ejb.thinclient_8.5.0.jar&#8217;
            </p>
            
            <p>
              WASX7209I: Connected to process &#8220;dmgr&#8221; on node DMGRNode using SOAP connector;  The type of process is: DeploymentManager
            </p>
            
            <p>
              WASX7303I: The following options are passed to the scripting environment and are available as arguments that are stored in the argv variable: &#8220;[/opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/customized_monconfig.properties]&#8221;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Validating configuration file
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Loading configuration file.
            </p>
            
            <p>
              &#8211; Reading properties file /opt/IBM/WebSphere/AppServer/scripts.wbm/monConfig/customized_monconfig.properties
            </p>
            
            <p>
              &#8211; Resolving new cluster names.
            </p>
            
            <p>
              &#8211; Validating no white spaces in properties.
            </p>
            
            <p>
              &#8211; Validating cluster names are unique.
            </p>
            
            <p>
              &#8211; Validating only 1 or 3 clusters have been defined.
            </p>
            
            <p>
              &#8211; Associating capabilities with clusters.
            </p>
            
            <p>
              &#8211; Validating only 1 or 3 capabilities have been defined.
            </p>
            
            <p>
              &#8211; Resolving new cluster members.
            </p>
            
            <p>
              &#8211; Validating cluster member names are unique.
            </p>
            
            <p>
              &#8211; Resolving new node names.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Collecting current configuration
            </p>
            
            <p>
              &#8211; Retrieving current cell name.
            </p>
            
            <p>
              &#8211; Current cell name MonCell1
            </p>
            
            <p>
              &#8211; Retrieving existing cluster names.
            </p>
            
            <p>
              &#8211; Collecting a list of existing Clusters.
            </p>
            
            <p>
              &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;
            </p>
            
            <p>
              AdminClusterManagement: List server clusters
            </p>
            
            <p>
              Usage: AdminClusterManagement.listClusters()
            </p>
            
            <p>
              Return: List of the clusters in the cell.
            </p>
            
            <p>
              &#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;&#8212;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Retrieving existing cluster member names.
            </p>
            
            <p>
              &#8211; Collecting a list of existing Cluster Members.
            </p>
            
            <p>
              &#8211; Retrieving existing managed node names.
            </p>
            
            <p>
              &#8211; Collecting a list of existing Managed Nodes.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Validating new configuration
            </p>
            
            <p>
              &#8211; Validating configuration clusters are new.
            </p>
            
            <p>
              &#8211; Validating configuration cluster members are new.
            </p>
            
            <p>
              &#8211; Validating configuration nodes already exist.
            </p>
            
            <p>
              &#8211; Validating configuration nodes are IBM Business Monitor nodes.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Create new clusters and cluster members
            </p>
            
            <p>
              &#8211; Creating cluster MonAppCluster.
            </p>
            
            <p>
              &#8211; Creating cluster member MonAppServer01. Please wait&#8230;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Creating cluster MonMECluster.
            </p>
            
            <p>
              &#8211; Creating cluster member MonMEServer01. Please wait&#8230;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Creating cluster MonSupCluster.
            </p>
            
            <p>
              &#8211; Creating cluster member MonSupServer01. Please wait&#8230;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Deploying, configuring and running tasks for the Deployment Environment
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployCEIEventService.
            </p>
            
            <p>
              trying to set property oracle.jdbc.autoCommitSpecCompliant = false
            </p>
            
            <p>
              Checking [&#8221;]  for a match to {&#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              trying to set property eclipse.bundle.setTCCL = false
            </p>
            
            <p>
              Checking [&#8216;oracle.jdbc.autoCommitSpecCompliant(cells/MonCell1/nodes/Node/servers/MonAppServer01|server.xml#TypedProperty_1438889467095)&#8217;]  for a match to {&#8216;eclipse.bundle.setTCCL&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Checking: oracle.jdbc.autoCommitSpecCompliant against eclipse.bundle.setTCCL
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;eclipse.bundle.setTCCL&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              trying to set property oracle.jdbc.autoCommitSpecCompliant = false
            </p>
            
            <p>
              Checking [&#8221;]  for a match to {&#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              trying to set property eclipse.bundle.setTCCL = false
            </p>
            
            <p>
              Checking [&#8216;oracle.jdbc.autoCommitSpecCompliant(cells/MonCell1/nodes/Node/servers/MonMEServer01|server.xml#TypedProperty_1438889467993)&#8217;]  for a match to {&#8216;eclipse.bundle.setTCCL&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Checking: oracle.jdbc.autoCommitSpecCompliant against eclipse.bundle.setTCCL
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;eclipse.bundle.setTCCL&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              trying to set property oracle.jdbc.autoCommitSpecCompliant = false
            </p>
            
            <p>
              Checking [&#8221;]  for a match to {&#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;oracle.jdbc.autoCommitSpecCompliant&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              trying to set property eclipse.bundle.setTCCL = false
            </p>
            
            <p>
              Checking [&#8216;oracle.jdbc.autoCommitSpecCompliant(cells/MonCell1/nodes/Node/servers/MonSupServer01|server.xml#TypedProperty_1438889468886)&#8217;]  for a match to {&#8216;eclipse.bundle.setTCCL&#8217;: &#8216;false&#8217;}
            </p>
            
            <p>
              Checking: oracle.jdbc.autoCommitSpecCompliant against eclipse.bundle.setTCCL
            </p>
            
            <p>
              Creating: [[&#8216;name&#8217;, &#8216;eclipse.bundle.setTCCL&#8217;], [&#8216;value&#8217;, &#8216;false&#8217;]]
            </p>
            
            <p>
              &#8211; Configuring runWbmConfigureEventEmitterFactory
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployMessagingEngine.
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployActionServices.
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployDefAsync.
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployScheduledServices.
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployEventEmitterServices.
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployBPMEmitterService.
            </p>
            
            <p>
              &#8211; Running configureCognosService
            </p>
            
            <p>
              &#8211; Deploying runWbmDeployDashboardsForMobileDevices.
            </p>
            
            <p>
              &#8211; Installing installRESTGatewayService
            </p>
            
            <p>
              ADMA0073W: Custom permissions are found in the [(&#8220;java.security.AllPermission&#8221; &#8220;<all permissions>&#8221; &#8220;<all actions>&#8221;)] policy file. Custom permissions can compromise the integrity of Java 2 Security.
            </p>
            
            <p>
              WASX7327I: Contents of was.policy file:
            </p>
            
            <p>
              grant codeBase &#8220;file:${application}&#8221; {
            </p>
            
            <p>
              permission java.security.AllPermission;
            </p>
            
            <p>
              };
            </p>
            
            <p>
              ADMA5016I: Installation of REST Services Gateway started.
            </p>
            
            <p>
              ADMA5058I: Application and module versions are validated with versions of deployment targets.
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5081I: The bootstrap address for client module is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5053I: The library references for the installed optional package are created.
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5001I: The application binaries are saved in /opt/IBM/WebSphere/AppServer/profiles/Dmgr01/wstemp/Script14f047c0898/workspace/cells/MonCell1/applications/REST Services Gateway.ear/REST Services Gateway.ear
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              SECJ0400I: Successfully updated the application REST Services Gateway with the appContextIDForSecurity information.
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5005I: The application REST Services Gateway is configured in the WebSphere Application Server repository.
            </p>
            
            <p>
              ADMA5113I: Activation plan created successfully.
            </p>
            
            <p>
              ADMA5011I: The cleanup of the temp directory for application REST Services Gateway is complete.
            </p>
            
            <p>
              ADMA5013I: Application REST Services Gateway installed successfully.
            </p>
            
            <p>
              &#8211; Deploying runUpdateRESTGatewayService.
            </p>
            
            <p>
              &#8211; Running installBusinessSpace
            </p>
            
            <p>
              &#8211; Running configureBusinessSpace
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Perform the following to complete the configuration prior to
            </p>
            
            <p>
              &#8211; starting the new cluster(s) and cluster member(s):
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211; Make sure that you are using a user ID with sufficient authority to
            </p>
            
            <p>
              &#8211; create tables.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;   1. Copy the database scripts from the profile you most recently
            </p>
            
            <p>
              &#8211;    configured to a directory on the database system.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;    The scripts are located in
            </p>
            
            <p>
              &#8211;    /opt/IBM/WebSphere/AppServer/profiles/Dmgr01/dbscripts/BusinessSpace
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;   2. Open a command prompt on your database system and run
            </p>
            
            <p>
              &#8211;    configBusinessSpaceDB.sh/.bat based on that operating system.
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;    For DB2 for z/OS, run the following files in order:
            </p>
            
            <p>
              &#8211;      createTablespace_BusinessSpace.sql
            </p>
            
            <p>
              &#8211;      createTable_BusinessSpace.sql
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;   Restart the deployment manager and all nodes.
            </p>
            
            <p>
              &#8211;   Then start the new cluster(s).
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              &#8211;   SUCCESS: The Monitor DE has been created successfully.
            </p>
            
            <p>
              PROCEEED TO STEP 5.
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-15" class="clarify-step-container">
      <h3 class="clarify-step-title">
        2. Execute Database scripts
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          At this point you will have scripts created in /opt/IBM/WebSphere/AppServer/profiles/Dmgr01/dbscripts (DEV) or in /opt/WebSphere/AppServer/profiles/Dmgr01/dbscripts (QA)
        </p>
        
        <p>
          You will need to provide those to your DBA to get the MONITOR and COGNOS schemas created. You will have some additional scripts for BusinessSpace to give to the DBA after you create the deployment environment.
        </p>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-16" class="clarify-step-container">
      <h3 class="clarify-step-title">
        3. Execute BusinessSpace database scripts
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          At this point you will have scripts created in /opt/IBM/WebSphere/AppServer/profiles/Dmgr01/dbscripts (DEV) or in /opt/WebSphere/AppServer/profiles/Dmgr01/dbscripts (QA)
        </p>
        
        <p>
          You will need to provide those to your DBA to get the BusinessSpace tables created. DO NOT START YOUR ENVIRONMENT UNTIL THESE SCRIPTS HAVE COMPLETED SUCCESSFULLY.
        </p>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-17" class="clarify-step-container">
      <h3 class="clarify-step-title">
        4. Start your environment
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          You will want to start your JVMs here one at a time, as there needs to be some first time initialization that has to occur, specifically with the Support server for Cognos. So, please start one server at a time in this order:
        </p>
        
        <p>
          Messaging
        </p>
        
        <p>
          Support
        </p>
        
        <p>
          Application
        </p>
        
        <p>
          Tail the logs and look for successful startup.
        </p>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
  </div>
</div>