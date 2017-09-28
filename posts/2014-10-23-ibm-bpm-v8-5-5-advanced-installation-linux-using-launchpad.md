---
title: IBM BPM v8.5.5 Advanced Installation on Linux
author: Seth
type: post
date: 2014-10-23T13:01:54+00:00
url: /ibm-bpm-v8-5-5-advanced-installation-linux-using-launchpad/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - "BPM Product How To's"
tags:
  - BPM
  - bpm installation
  - business process manager
  - IBM BPM
  - IBM Business Monitor
  - Process Center
  - websphere

---
<div class="clarify-article-content">
  <div class="clarify-article-description">
    <p>
      This How To article describes how to install IBM Business Process Manager Advanced v8.5.5 on Linux. The Launchpad is used to start the Custom installation process and I then use the BPMConfig command to create and configure the deployment environment, after the binaries have been installed.
    </p>
  </div>
</div>

<!--more-->

<div class="clarify-article-content">
  <div class="clarify-steps-container">
    <div id="clarify-step-15" class="clarify-step-container">
      <h4 class="clarify-step-title">
        1. Installing IBM BPM v8.5.5 Advanced Binaries
      </h4>
      
      <div class="clarify-step-instructions">
        <p>
          The following steps outline how to prep your Linux system and install the BPM binaries.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-1" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.1 Extract binaries to a common directory
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              After you have downloaded your IBM BPM Advanced binaries for Linux, you will need to untar them all to a common directory. Your directory structure should look like the figure below:
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/extract-binaries-to-a-common-directory.png?resize=591%2C226" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-10" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.2 Preparation of the Linux Operation System
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              The Linux operating system needs to be prepped in order to install BPM successfully. Please perform the following steps found here:
            </p>
            
            <p>
              <a href="http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.imuc.ebpm.doc/topics/prep_bpm_os_lin.html">http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.imuc.ebpm.doc/topics/prep_bpm_os_lin.html</a>
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-2" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.3 Run the Launchpad
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              Please ensure you are running the Launchpad as a root user.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/run-the-launchpad.png?resize=900%2C754" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-3" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.4 Select custom installation
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Select the custom install option on the left menu
              </li>
              <li>
                Verify that the Install as administrative user checkbox is checked
              </li>
              <li>
                Click Install
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/select-custom-installation.png?resize=900%2C566" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-4" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.5 Installation Manager will now open
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Here you will see the Installation Manager screen open and it will show the components of the BPM product that will be installed on the system.
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/installation-manager-will-now-open.png?resize=900%2C566" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-5" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.6 Select fixes to install
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Installation Manager will recommend a series of fixes to install with this installation. Select all the fixes.
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/select-fixes-to-install.png?resize=900%2C566" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-6" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.7 Prerequisite check
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                You may see an error like this if you are installing this on an unsupported OS. In this example, I am installing on CentOS, which is technically not a supported OS from IBM for the BPM product.
              </li>
              <li>
                Click Next to ignore this error.
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/prerequisite-check.png?resize=900%2C566" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-7" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.8 Accept license agreement
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Scoll to the bottom of the license agreement
              </li>
              <li>
                Ensure you accept the terms
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/accept-license-agreement.png?resize=900%2C566" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-8" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.9 Select an install location for Installation Manager
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Validate the Shared Resources installation location
              </li>
              <li>
                Validate the install location for the Installation Manager
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/select-an-install-location-for-installation-manager.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-9" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.10 Select the WebSphere Application Server location
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Confirm the installation location for where WebSphere Application Server will be installed.
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/select-the-websphere-application-server-location.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-11" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.11 Confirm your language selection
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Confirm your language
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/confirm-your-language-selection.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-12" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.12 Select the packages to install
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                In this example, we want to install a Process Center environment, so confirm that Process Center is selected.
              </li>
              <li>
                Also, confirm that the Case Management package is selected, should you want to make use of that component.
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/select-the-packages-to-install.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-13" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.13 Enter DB2 credentials
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Create a DB2 instance user. I chose username: dbadmin pass: dbadmin
              </li>
              <li>
                Create a DB2 fenced user. I chose username: dbadminf pass: dbadminf
              </li>
              <li>
                Create a DB2 DAS user. I chose username: dbadmind pass: dbadmind
              </li>
              <li>
                Click Next
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/enter-db2-credentials.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-14" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.14 Review summary and Install
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Review installation packages and locations
              </li>
              <li>
                Click Install
              </li>
            </ol>
            
            <p>
              This process can take some time for everything to install. Keep an eye on the screen every once in a while for any errors.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/review-summary-and-install.png?resize=900%2C573" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-17" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            1.15 Look for Successful Installation
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Confirm the packages are installed
              </li>
              <li>
                Under Which program do you want to start?, select None
              </li>
              <li>
                Click FInish
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/look-for-successful-installation.png?resize=900%2C529" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-18" class="clarify-step-container">
      <h4 class="clarify-step-title">
        2. Create your Shell DB2 Databases
      </h4>
      
      <div class="clarify-step-instructions">
        <p>
          Before we create our deployment environment, we must manually create the required databases in DB2.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-19" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            2.1 Create the BPM required databases.
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              The BPM product provides scripts that you can run so that you can manually create the required databases. The product requires three databases: BPMDB, PDWDB, CMNDB. Additional information can be found here:
            </p>
            
            <p>
              <a href="http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.imuc.ebpm.doc/topics/db_create_nd_lin_db2.html">http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.imuc.ebpm.doc/topics/db_create_nd_lin_db2.html</a>
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-20" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            2.2 Create the BPMDB script.
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              Edit the createDatabase.sql script found in BPM_HOME/BPM/dbscripts/DB2/Create. Replace @DB_NAME@ with the name that you want to use for the created database and @DB_USER@ with the user name that you want to use for the database.
            </p>
            
            <p>
              For the BPMDB it should look like this:
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/create-the-bpmdb-script.png?resize=843%2C558" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-22" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            2.3 Ensure DB2 is started
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              Navigate to /opt/WebSphere/AppServer/db2/adm and run ./db2start
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/ensure-db2-is-started.png?resize=843%2C558" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-21" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            2.4 Run the script
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                After you have edited the createDatabase.sql, you an run the createDatabase.sh script to create the first database. Navigate to /opt/IBM/WebSphere/AppServer/db2/bin and run ./db2 -tvf /opt/IBM/WebSphere/AppServer/BPM/dbscripts/DB2/Create/createDatabase.sql
              </li>
              <li>
                Look for Success messages
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/run-the-script.png?resize=843%2C558" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-23" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            2.5 Re-run the script for the other two databases
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              In the previous step, you created the BPMDB. Now you need to edit the script again like you did in step 2.2.
            </p>
            
            <ol>
              <li>
                Repeat steps 2.2 through 2.4 for the creation of the PDWDB and the creation of the CMNDB. See the success images for both databases below.
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/re-run-the-script-for-the-other-two-databases.png?resize=843%2C1102" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-16" class="clarify-step-container">
      <h4 class="clarify-step-title">
        3. Creating the Deployment Environment
      </h4>
      
      <div class="clarify-step-instructions">
        <p>
          Creating the deployment environment allows us to create our WebSphere profiles and also database tables and structures.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-24" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            3.1 Locate the sample BPMConfig properties file for your installation
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Navigate to /opt/IBM/WebSphere/AppServer/BPM/samples/config/advanced. Here you will find a list of various properties files that can be used to create the environment of your choice. In this example, we will be creating a Single Cluster Process Center environment, running with DB2 as the database.
              </li>
              <li>
                Open and review the Advanced-PC-SingleCluster-DB2.properties and edit as needed. Here is a copy of the properties file I used in this example:
              </li>
            </ol>
            
            <p>
              ##########################################
            </p>
            
            <p>
              # Deployment environment properties: De1 #
            </p>
            
            <p>
              ##########################################
            </p>
            
            <p>
              bpm.de.name=De1
            </p>
            
            <p>
              # The type of product configuration: Express, Standard, Advanced, or AdvancedOnly.
            </p>
            
            <p>
              bpm.de.type=Advanced
            </p>
            
            <p>
              # The type of deployment environment: Process Center or Process Server.
            </p>
            
            <p>
              bpm.de.environment=Process Center
            </p>
            
            <p>
              # Options: true or false. If false, the database schemas are created when the deployment environment is created. If true, they need to be created manually using the generated scripts, and the bootstrapProcessServerData script needs to be run manually.
            </p>
            
            <p>
              bpm.de.deferSchemaCreation=false
            </p>
            
            <p>
              # The context root prefix for all web modules in this environment. If set, the context root prefix must start with a forward slash character (/).
            </p>
            
            <p>
              bpm.de.contextRootPrefix=
            </p>
            
            <p>
              # The virtualHost for all web modules in this environment. If a value is not set for virtualHost, the default value &#8216;default_host&#8217; is used.
            </p>
            
            <p>
              bpm.de.virtualHost=
            </p>
            
            <p>
              ######################################################################################################################################################
            </p>
            
            <p>
              # Deployment environment administrator authentication alias, it cannot have the same user name as the authentication alias of the cell administrator #
            </p>
            
            <p>
              ######################################################################################################################################################
            </p>
            
            <p>
              bpm.de.authenticationAlias.1.name=DeAdminAlias
            </p>
            
            <p>
              bpm.de.authenticationAlias.1.user=bpmdeadmin
            </p>
            
            <p>
              bpm.de.authenticationAlias.1.password=bpmdeadmin
            </p>
            
            <p>
              ######################################
            </p>
            
            <p>
              # Database user authentication alias #
            </p>
            
            <p>
              ######################################
            </p>
            
            <p>
              bpm.de.authenticationAlias.2.name=BPM_DB_ALIAS
            </p>
            
            <p>
              bpm.de.authenticationAlias.2.user=dbadmin
            </p>
            
            <p>
              bpm.de.authenticationAlias.2.password=dbadmin
            </p>
            
            <p>
              #########################################################################################################################################################################################################################################################################################################################################################################################
            </p>
            
            <p>
              # The deployment environment administrator role and authentication alias association. If you do not specify the BPMAuthor role, the authentication alias that maps to this role will be used when Process Center connects to IBM Process Server for online deployment. It must be defined in both Process Server and Process Center, and the user names and passwords must be the same. #
            </p>
            
            <p>
              #########################################################################################################################################################################################################################################################################################################################################################################################
            </p>
            
            <p>
              # Do not modify the name of the role mapping. Role mapping names are predefined. Specify the user name in the authentication alias that corresponds to this role.
            </p>
            
            <p>
              bpm.de.roleMapping.1.name=DeAdmin
            </p>
            
            <p>
              bpm.de.roleMapping.1.alias=DeAdminAlias
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              ############################
            </p>
            
            <p>
              # Cell properties: PCCell1 #
            </p>
            
            <p>
              ############################
            </p>
            
            <p>
              bpm.cell.name=PCCell1
            </p>
            
            <p>
              # The database at the cell level. This database is only applicable to IBM BPM Advanced and AdvancedOnly configurations. The value should correspond to the name of a database that is defined in this file.
            </p>
            
            <p>
              bpm.cell.db=CellOnlyDb
            </p>
            
            <p>
              ##################################################
            </p>
            
            <p>
              # Cell (WAS) administration authentication alias #
            </p>
            
            <p>
              ##################################################
            </p>
            
            <p>
              bpm.cell.authenticationAlias.1.name=CellAdminAlias
            </p>
            
            <p>
              bpm.cell.authenticationAlias.1.user=bpmcelladmin
            </p>
            
            <p>
              bpm.cell.authenticationAlias.1.password=bpmcelladmin
            </p>
            
            <p>
              ##################################################
            </p>
            
            <p>
              # Cell role and authentication alias association #
            </p>
            
            <p>
              ##################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.cell.roleMapping.1.name=CellAdmin
            </p>
            
            <p>
              bpm.cell.roleMapping.1.alias=CellAdminAlias
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              #################################
            </p>
            
            <p>
              # Deployment manager properties #
            </p>
            
            <p>
              #################################
            </p>
            
            <p>
              # The name of the deployment manager node.
            </p>
            
            <p>
              bpm.dmgr.nodeName=Dmgr
            </p>
            
            <p>
              # The host name of the deployment manager. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.dmgr.hostname=localhost
            </p>
            
            <p>
              # The installation location of the BPM product. If you want to use a backslash character (\) in your properties file, you must use an escape backslash before it, for example bpm.dmgr.installPath=c:\\IBM\\BPM85.
            </p>
            
            <p>
              bpm.dmgr.installPath=/opt/IBM/WebSphere/AppServer
            </p>
            
            <p>
              # The name of the deployment manager profile.
            </p>
            
            <p>
              bpm.dmgr.profileName=DmgrProfile
            </p>
            
            <p>
              # To override the default port assignments for this profile, specify a starting port number for generating and assigning ports.
            </p>
            
            <p>
              bpm.dmgr.initialPortAssignment=
            </p>
            
            <p>
              # The deployment manager SOAP port. This port is used to establish a connection to the deployment manager during the creation of remote nodes. Update this property after you create the deployment manager profile.
            </p>
            
            <p>
              bpm.dmgr.soapPort=8879
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              #####################################
            </p>
            
            <p>
              # Cluster properties: SingleCluster #
            </p>
            
            <p>
              #####################################
            </p>
            
            <p>
              bpm.de.cluster.1.name=SingleCluster
            </p>
            
            <p>
              # Options: Application, Support, Messaging. These three capabilities correspond to the three-cluster topology that is supported by IBM BPM. If this is a single-cluster environment, specify all three of these capabilities here.
            </p>
            
            <p>
              bpm.de.cluster.1.capabilities=Application,Messaging,Support
            </p>
            
            <p>
              # The list of databases that are used on this cluster. Each value should correspond to the name of a database defined in this file. For a single-cluster topology, the list should include all of the databases that are used (with the exception of the CellOnlyDb in IBM BPM Advanced environments). For a three-cluster topology, the Application cluster includes all of the databases except those that are used for messaging and the Performance Data Warehouse (PDW). The messaging and PDW databases are included in the Messaging and Support clusters.
            </p>
            
            <p>
              bpm.de.cluster.1.db=ProcessServerDb,SharedDb,PerformanceDb
            </p>
            
            <p>
              bpm.de.cluster.1.capability.1.component.1.name=ProcessPortal
            </p>
            
            <p>
              # The context root prefix for all web modules in the specified component. If set, the context root prefix must start with a forward slash character (/).
            </p>
            
            <p>
              bpm.de.cluster.1.capability.1.component.1.contextRootPrefix=
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              ##########################
            </p>
            
            <p>
              # Node properties: Node1 #
            </p>
            
            <p>
              ##########################
            </p>
            
            <p>
              bpm.de.node.1.name=Node1
            </p>
            
            <p>
              # If the host name is the same as deployment manager, this node will be created on the same computer. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.de.node.1.hostname=localhost
            </p>
            
            <p>
              # The installation location of the BPM product. If you want to use a backslash character (\) in your properties file, you must use an escape backslash before it, for example bpm.de.node.1.installPath=c:\\IBM\\BPM85.
            </p>
            
            <p>
              bpm.de.node.1.installPath=/opt/IBM/WebSphere/AppServer
            </p>
            
            <p>
              # The name of the node profile.
            </p>
            
            <p>
              bpm.de.node.1.profileName=Node1Profile
            </p>
            
            <p>
              # To override the default port assignments for this profile, specify a starting port number for generating and assigning ports.
            </p>
            
            <p>
              bpm.de.node.1.initialPortAssignment=
            </p>
            
            <p>
              ###################################################
            </p>
            
            <p>
              # Cluster member properties: SingleClusterMember1 #
            </p>
            
            <p>
              ###################################################
            </p>
            
            <p>
              bpm.de.node.1.clusterMember.1.name=SingleClusterMember1
            </p>
            
            <p>
              # The cluster this cluster member belongs to. This value should correspond to the name of a cluster defined in this file.
            </p>
            
            <p>
              bpm.de.node.1.clusterMember.1.cluster=SingleCluster
            </p>
            
            <p>
              # The proportion of requests that are sent to this cluster member
            </p>
            
            <p>
              bpm.de.node.1.clusterMember.1.weight=2
            </p>
            
            <p>
              bpm.de.node.1.clusterMember.1.initialPortAssignment=
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              #################################
            </p>
            
            <p>
              # Database properties: SharedDb #
            </p>
            
            <p>
              #################################
            </p>
            
            <p>
              # Keyword to use to refer to this set of database properties. This is not the database name.
            </p>
            
            <p>
              bpm.de.db.1.name=SharedDb
            </p>
            
            <p>
              # The list of available options depends on the product configuration. For IBM BPM Express and Standard, the options are ProcessServer, EmbeddedECM, PDW, Messaging, and BusinessSpace. For IBM BPM Advanced, the options are ProcessServer, EmbeddedECM, PDW, CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For IBM BPM Advanced Only, the options are CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For EmbeddedECM, there is no support if the operating system for the IBM BPM environment is z/OS.
            </p>
            
            <p>
              bpm.de.db.1.dbCapabilities=Messaging,BusinessSpace,CommonDB,BPC
            </p>
            
            <p>
              # Options: DB2, DB2zOS, Oracle, or SQL Server.
            </p>
            
            <p>
              bpm.de.db.1.type=DB2
            </p>
            
            <p>
              # The host name of the database. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.de.db.1.hostname=localhost
            </p>
            
            <p>
              bpm.de.db.1.portNumber=50000
            </p>
            
            <p>
              # The name of the database.
            </p>
            
            <p>
              bpm.de.db.1.databaseName=CMNDB
            </p>
            
            <p>
              bpm.de.db.1.schema=dbadmin
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.1.roleMapping.1.name=DbUser
            </p>
            
            <p>
              bpm.de.db.1.roleMapping.1.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.1.roleMapping.2.name=DbUserXAR
            </p>
            
            <p>
              bpm.de.db.1.roleMapping.2.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              ########################################
            </p>
            
            <p>
              # Database properties: ProcessServerDb #
            </p>
            
            <p>
              ########################################
            </p>
            
            <p>
              # Keyword to use to refer to this set of database properties. This is not the database name.
            </p>
            
            <p>
              bpm.de.db.2.name=ProcessServerDb
            </p>
            
            <p>
              # The list of available options depends on the product configuration. For IBM BPM Express and Standard, the options are ProcessServer, EmbeddedECM, PDW, Messaging, and BusinessSpace. For IBM BPM Advanced, the options are ProcessServer, EmbeddedECM, PDW, CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For IBM BPM Advanced Only, the options are CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For EmbeddedECM, there is no support if the operating system for the IBM BPM environment is z/OS.
            </p>
            
            <p>
              bpm.de.db.2.dbCapabilities=ProcessServer,EmbeddedECM
            </p>
            
            <p>
              # Options: DB2, DB2zOS, Oracle, or SQL Server.
            </p>
            
            <p>
              bpm.de.db.2.type=DB2
            </p>
            
            <p>
              # The host name of the database. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.de.db.2.hostname=localhost
            </p>
            
            <p>
              bpm.de.db.2.portNumber=50000
            </p>
            
            <p>
              # The name of the database.
            </p>
            
            <p>
              bpm.de.db.2.databaseName=BPMDB
            </p>
            
            <p>
              bpm.de.db.2.schema=dbadmin
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.2.roleMapping.1.name=DbUser
            </p>
            
            <p>
              bpm.de.db.2.roleMapping.1.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.2.roleMapping.2.name=DbUserXAR
            </p>
            
            <p>
              bpm.de.db.2.roleMapping.2.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              ######################################
            </p>
            
            <p>
              # Database properties: PerformanceDb #
            </p>
            
            <p>
              ######################################
            </p>
            
            <p>
              # Keyword to use to refer to this set of database properties. This is not the database name.
            </p>
            
            <p>
              bpm.de.db.3.name=PerformanceDb
            </p>
            
            <p>
              # The list of available options depends on the product configuration. For IBM BPM Express and Standard, the options are ProcessServer, EmbeddedECM, PDW, Messaging, and BusinessSpace. For IBM BPM Advanced, the options are ProcessServer, EmbeddedECM, PDW, CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For IBM BPM Advanced Only, the options are CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For EmbeddedECM, there is no support if the operating system for the IBM BPM environment is z/OS.
            </p>
            
            <p>
              bpm.de.db.3.dbCapabilities=PDW
            </p>
            
            <p>
              # Options: DB2, DB2zOS, Oracle, or SQL Server.
            </p>
            
            <p>
              bpm.de.db.3.type=DB2
            </p>
            
            <p>
              # The host name of the database. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.de.db.3.hostname=localhost
            </p>
            
            <p>
              bpm.de.db.3.portNumber=50000
            </p>
            
            <p>
              # The name of the database.
            </p>
            
            <p>
              bpm.de.db.3.databaseName=PDWDB
            </p>
            
            <p>
              bpm.de.db.3.schema=dbadmin
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.3.roleMapping.1.name=DbUser
            </p>
            
            <p>
              bpm.de.db.3.roleMapping.1.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.3.roleMapping.2.name=DbUserXAR
            </p>
            
            <p>
              bpm.de.db.3.roleMapping.2.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              &nbsp;
            </p>
            
            <p>
              ###################################
            </p>
            
            <p>
              # Database properties: CellOnlyDb #
            </p>
            
            <p>
              ###################################
            </p>
            
            <p>
              # Keyword to use to refer to this set of database properties. This is not the database name.
            </p>
            
            <p>
              bpm.de.db.4.name=CellOnlyDb
            </p>
            
            <p>
              # The list of available options depends on the product configuration. For IBM BPM Express and Standard, the options are ProcessServer, EmbeddedECM, PDW, Messaging, and BusinessSpace. For IBM BPM Advanced, the options are ProcessServer, EmbeddedECM, PDW, CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For IBM BPM Advanced Only, the options are CellScopedDB, Messaging, BusinessSpace, CommonDB, and BPC. For EmbeddedECM, there is no support if the operating system for the IBM BPM environment is z/OS.
            </p>
            
            <p>
              bpm.de.db.4.dbCapabilities=CellScopedDB
            </p>
            
            <p>
              # Options: DB2, DB2zOS, Oracle, or SQL Server.
            </p>
            
            <p>
              bpm.de.db.4.type=DB2
            </p>
            
            <p>
              # The host name of the database. Do not use localhost for environments that span multiple hosts.
            </p>
            
            <p>
              bpm.de.db.4.hostname=localhost
            </p>
            
            <p>
              bpm.de.db.4.portNumber=50000
            </p>
            
            <p>
              # The name of the database.
            </p>
            
            <p>
              bpm.de.db.4.databaseName=CMNDB
            </p>
            
            <p>
              bpm.de.db.4.schema=dbadmin
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.4.roleMapping.1.name=DbUser
            </p>
            
            <p>
              bpm.de.db.4.roleMapping.1.alias=BPM_DB_ALIAS
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Database role and authentication alias associations #
            </p>
            
            <p>
              #######################################################
            </p>
            
            <p>
              # Do not modify this value. Role mapping names are predefined. Specify the user name in the authentication alias corresponding to this role.
            </p>
            
            <p>
              bpm.de.db.4.roleMapping.2.name=DbUserXAR
            </p>
            
            <p>
              bpm.de.db.4.roleMapping.2.alias=BPM_DB_ALIAS
            </p>
            
            <ol>
              <li value="3">
                Run the following command from /opt/IBM/WebSphere/AppServer/bin:
              </li>
            </ol>
            
            <p>
              ./BPMConfig.sh -create -de /opt/IBM/WebSphere/AppServer/BPM/samples/config/advanced/Advanced-PC-SingleCluster-DB2-Sample.properties
            </p>
            
            <p>
              This command will take a while to complete.
            </p>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-25" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            3.2 Look for successful completion
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              After the command completes, you will see a successfully completed message.
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/look-for-successful-completion.png?resize=843%2C527" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
    
    <div id="clarify-step-26" class="clarify-step-container">
      <h4 class="clarify-step-title">
        4. Starting your Deployment Environment.
      </h4>
      
      <div class="clarify-step-instructions">
        <p>
          You can now start your deployment environment for the first time. We do not need to populate the database tables using the bootstrap command, as we set the <strong>bpm.de.deferSchemaCreation parameter to false</strong>. Let&#8217;s start with the Deployment Manager and Node Agent.
        </p>
      </div>
      
      <div class="clarify-sub-steps-container">
        <div id="clarify-step-27" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            4.1 Start the deployment manager
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Navigate to /opt/IBM/WebSphere/AppServer/profiles/DmgrProfile/bin and run ./startManager.sh
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/start-the-deployment-manager.png?resize=843%2C528" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-28" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            4.2 Start the node agent
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Navigate to /opt/IBM/WebSphere/AppServer/profiles/Node1Profile/bin and run ./startNode.sh
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/start-the-node-agent.png?resize=843%2C528" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-29" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            4.3 Login to WAS console
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Launch a browser and go to <a href="https://localhost:9043/ibm/console">https://localhost:9043/ibm/console</a> and login with username: bpmdeadmin password: bpmdeadmin. You should then be presented with the screen below.
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/login-to-was-console.png?resize=900%2C361" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-30" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            4.4 Start the application servers.
          </h5>
          
          <div class="clarify-step-instructions">
            <ol>
              <li>
                Navigate to Servers > Server Types > WebSphere application servers
              </li>
              <li>
                Click the checkbox next to the application server
              </li>
              <li>
                Click Start
              </li>
            </ol>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/start-the-application-servers.png?resize=900%2C361" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
        
        <div id="clarify-step-31" class="clarify-sub-step-container">
          <h5 class="clarify-step-title">
            4.5 Look for successful startup message.
          </h5>
          
          <div class="clarify-step-instructions">
            <p>
              Once the server is up and running, you can now access Process Center and download Process Designer. Sometimes the server can take a long time to startup and the console will timeout. So, you will want to confirm in the logs directory in the SystemOut.log file to ensure a successful startup. The product is now fully installed and ready to use. Here is the InfoCenter link fo any additional information on the product.
            </p>
            
            <p>
              <a href="http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.main.doc/kc-homepage-bpm.html">http://www-01.ibm.com/support/knowledgecenter/SSFPJS_8.5.5/com.ibm.wbpm.main.doc/kc-homepage-bpm.html</a>
            </p>
            
            <p>
              Here are some relevant URLs that are related to this installation:
            </p>
            
            <p>
              <a href="https://localhost:9443/ProcessCenter">https://localhost:9443/ProcessCenter</a>
            </p>
            
            <p>
              <a href="https://localhost:9443/ProcessPortal">https://localhost:9443/ProcessPortal</a>
            </p>
            
            <p>
              &nbsp;
            </p>
          </div>
          
          <div class="clarify-step-image-wrapper">
            <div class="clarify-step-image-container">
              <img class="clarify-step-image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/10/look-for-successful-startup-message.png?resize=900%2C361" alt="" data-recalc-dims="1" />
            </div>
          </div>
        </div>
        
        <div class="clarify-clear">
        </div>
      </div>
    </div>
    
    <div class="clarify-clear">
    </div>
  </div>
</div>