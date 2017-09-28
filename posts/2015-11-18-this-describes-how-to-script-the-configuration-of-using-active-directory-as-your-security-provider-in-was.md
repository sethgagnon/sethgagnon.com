---
title: This describes how to script the configuration of using Active Directory as your security provider in WAS.
author: Seth
type: post
date: 2015-11-18T13:00:35+00:00
url: /this-describes-how-to-script-the-configuration-of-using-active-directory-as-your-security-provider-in-was/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - General IBM
  - WebSphere Application Server

---
<div class="clarify-article-content">
  <div class="clarify-steps-container">
    <div id="clarify-step-1" class="clarify-step-container">
      <h3 class="clarify-step-title">
        1. Configuring Active Directory as your Security Provider for IBM Business Monitor 8.5.6 or IBM Business Process Manager 8.5.6
      </h3>
      
      <div class="clarify-step-instructions">
        <p>
          Stop your applications servers in the correct order (App, Support, ME) and then from the DMGR server, launch a wsadmin session:
        </p>
        
        <p>
          /opt/IBM/WebSphere/AppServer/profiles/Dmgr01/bin/wsadmin.sh -user wsadmin -password PASSWORD -lang jython
        </p>
        
        <p>
          Run the following commands:
        </p>
        
        <p>
          AdminTask.createIdMgrLDAPRepository(&#8216;[-default true -id <em>ADNAME</em> -adapterClassName com.ibm.ws.wim.adapter.ldap.LdapAdapter -ldapServerType AD -sslConfiguration  -certificateMapMode exactdn -supportChangeLog none -certificateFilter  -loginProperties uid]&#8217;)
        </p>
        
        <p>
          AdminTask.addIdMgrLDAPServer(&#8216;[-id <em>ADNAME</em> -host <em>ADHOSTNAME</em> -bindDN BINDUSERID -bindPassword PASSWORD -referal ignore -sslEnabled false -ldapServerType AD -sslConfiguration  -certificateMapMode exactdn -certificateFilter  -authentication simple -port 389]&#8217;)
        </p>
        
        <p>
          AdminTask.addIdMgrRepositoryBaseEntry(&#8216;[-id ADNAME -name DC=DCNAMES -nameInRepository DCNAMES]&#8217;)
        </p>
        
        <p>
          AdminTask.addIdMgrRealmBaseEntry(&#8216;[-name defaultWIMFileBasedRealm -baseEntry DCNAMES]&#8217;)
        </p>
        
        <p>
          AdminConfig.save()
        </p>
        
        <p>
          &nbsp;
        </p>
        
        <p>
          After the save you can restart your Dmgr and nodes.
        </p>
        
        <p>
          &nbsp;
        </p>
        
        <p>
          ADNAME = This is the ID of your Active Directory repository
        </p>
        
        <p>
          ADHOSTNAME = This is the host name where your Active Directory resides
        </p>
        
        <p>
          BINDUSERID = This is the user ID that you will use to bind to Active Dorectory
        </p>
        
        <p>
          PASSWORD = This is the password for the BINDUSERID
        </p>
        
        <p>
          DCNAMES = Ths is the name of the Domain Components you are using in Active Directory
        </p>
      </div>
    </div>
  </div>
</div>