---
title: Configuring Business Monitor for Event Consumption from WebSphere MQ
author: Seth
type: post
date: 2014-06-11T22:04:31+00:00
url: /configuring-business-monitor-event-consumption-websphere-mq-2/
kalinsPDFMeta:
  - '{"showLink":"top"}'
categories:
  - Business Monitor
tags:
  - business monitor
  - event consumption
  - events
  - IBM Business Monitor
  - monitor
  - MQ
  - websphere

---
  


<p align="right">
  -- <a href="http://sethgagnon.com/wp-content/plugins/kalins-pdf-creation-station/kalins_pdf_create.php?singlepost=po_1257" target="_blank" >Download Configuring Business Monitor for Event Consumption from WebSphere MQ as PDF</a> --
</p>

  


### Overview

The document outlines how to configure the Business Monitor infrastructure to consume events from a WebSphere MQ Queue. Please note that some of the images may have blocked out content. This is to ensure privacy of the actual content that was used in the screen shots.

There is some pre-requisite information that you will need before configuring the infrastructure:

1.    Host name of the MQ server
  
2.    Queue manager name
  
3.    Port
  
4.    Queue name
  
5.    Server connection channel

There are four parts to setting up this infrastructure:

Part I – Create a Queue Connection Factory
  
Part II – Create a Queue
  
Part III – Create an Event Listener
  
Part IV – Deploy and Configure the MDB application

### Part I – Create a Queue Connection Factory

First, you will need to create a Queue Connection Factory in the WebSphere Business Monitor admin console.

Navigate to Resources > JMS > Queue connection factories. Select the scope for where you want to create the resource (Support cluster in this case). Click New.

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb32.png?resize=644%2C113" alt="image" border="0" data-recalc-dims="1" />][1]

Select WebSphere MQ messaging provider and click OK:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb33.png?resize=644%2C193" alt="image" border="0" data-recalc-dims="1" />][2]

Enter a Name and JNDI name for this connection factory. Remember this information as you will need it later. Click Next.

[<img class="alignnone wp-image-1259 " src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-3-300x113.png?resize=348%2C113" alt="" data-recalc-dims="1" />][3]

Select Enter all the required information into this wizard and click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb35.png?resize=644%2C195" alt="image" border="0" data-recalc-dims="1" />][4]

Enter the Queue Manager name and click Next:

[<img class="alignnone size-medium wp-image-1265" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-5-300x121.png?resize=300%2C121" alt="Figure 5" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-5.png?resize=300%2C121 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-5.png?w=909 909w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][5]

&nbsp;

For the Transport, select Client. Enter the hostname and port for the MQ server, as well as, the Server connection channel. Click Next:

[<img class="alignnone size-medium wp-image-1266" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-6-300x142.png?resize=300%2C142" alt="Figure 6" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-6.png?resize=300%2C142 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-6.png?w=908 908w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][6]

Click Test connection:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb38.png?resize=644%2C303" alt="image" border="0" data-recalc-dims="1" />][7]

Look for successful connection message:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb39.png?resize=644%2C295" alt="image" border="0" data-recalc-dims="1" />][8]

Review Summary and Click Finish:

[<img class="alignnone size-medium wp-image-1267" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-9-300x134.png?resize=300%2C134" alt="Figure 9" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-9.png?resize=300%2C134 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-9.png?w=911 911w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][9]

Click on Save to save changes to master repository:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb41.png?resize=644%2C134" alt="image" border="0" data-recalc-dims="1" />][10]

### Part II – Create a Queue

You will now need to create a Queue in the WebSphere Business Monitor admin console.

Navigate to Resources > JMS > Queues. Select the scope for where you want to create the resource (Support cluster in this case). Click New:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb42.png?resize=644%2C174" alt="image" border="0" data-recalc-dims="1" />][11]

Select WebSphere MQ messaging provider and click OK:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb43.png?resize=644%2C218" alt="image" border="0" data-recalc-dims="1" />][12]

Enter a Name and JNDI name. Remember this information as you will need it later. Also enter the Queue name of the MQ Queue and click OK:

[<img class="alignnone size-medium wp-image-1268" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-13-300x249.png?resize=300%2C249" alt="Figure 13" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-13.png?resize=300%2C249 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-13.png?w=922 922w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][13]

Click on Save to save changes to master repository:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb45.png?resize=644%2C134" alt="image" border="0" data-recalc-dims="1" />][14]

### Part III – Create an Event Listener

You will now create an event listener on the servers that will be running the MDB application. In this case, the Support cluster.

Navigate to Servers > Server Types > WebSphere application servers > server name > Communications > Messaging > Messaging listener service > Listener ports and click New:

[<img class="alignnone size-medium wp-image-1269" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-15-300x87.png?resize=300%2C87" alt="Figure 15" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-15.png?resize=300%2C87 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-15.png?w=935 935w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][15]

Enter the Name, Connection Factory JNDI name (Connection Factory JNDI from Part 1), Destination JNDI name (Queue JNDI from Part 2). You can also change the Initial State to either be Started or Stopped.  If Started is elected, this will cause the listener to automatically start up and pull message off the MQ queue if the Support server is restarted. If Stop is selected, this will cause the listener to remain down upon Support server restart and messages will NOT be pulled from the MQ queue. Click OK:

[<img class="alignnone size-medium wp-image-1270" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-16-300x209.png?resize=300%2C209" alt="Figure 16" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-16.png?resize=300%2C209 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-16.png?w=924 924w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][16]

Click Save to save changes to master repository:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb48.png?resize=628%2C132" alt="image" border="0" data-recalc-dims="1" />][17]

Repeat these same steps to create the listener on the other server(s) that are part of your cluster. If you are only pulling message from one MQ queue, then only on of these listeners need to be up and running at a time.

### Part IV – Deploy and Configure the MDB application

The last part of this infrastructure configuration requires the setup of an MDB application that will be used to pull messages off of the MQ queue and put them in Business Monitor CEI for event consumption. The Business Monitor product comes with this application. We will simply be modifying the existing application so that we can deploy another version of it that will be specific to our event consumption.

In the Business Monitor admin console, navigate to Applications > Application Types > WebSphere enterprise applications. Select the check box next to IBM\_WBM\_EMITTER_SERVICES and click Export:

[<img class="alignnone size-medium wp-image-1271" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-18-300x198.png?resize=300%2C198" alt="Figure 18" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-18.png?resize=300%2C198 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-18.png?w=903 903w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][18]

Click on the file (ear) and save it on your local machine:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb50.png?resize=553%2C113" alt="image" border="0" data-recalc-dims="1" />][19]

Navigate back to Applications > Application Types > WebSphere enterprise applications and click Install:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb51.png?resize=549%2C134" alt="image" border="0" data-recalc-dims="1" />][20]

Select Choose file and select the ear file you saved on your local machine in the previous step and click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb52.png?resize=548%2C227" alt="image" border="0" data-recalc-dims="1" />][21]

Select Detailed and click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb53.png?resize=548%2C153" alt="image" border="0" data-recalc-dims="1" />][22]

Click Continue if this message appears:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb54.png?resize=547%2C168" alt="image" border="0" data-recalc-dims="1" />][23]

Enter a unique Application name for this app under the Application name section and click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb55.png?resize=541%2C484" alt="image" border="0" data-recalc-dims="1" />][24]

Make sure to select the Support cluster for this application to be deployed onto and click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb56.png?resize=565%2C484" alt="image" border="0" data-recalc-dims="1" />][25]

Click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb57.png?resize=566%2C484" alt="image" border="0" data-recalc-dims="1" />][26]

Click Next:

[<img class="alignnone size-medium wp-image-1273" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-27-300x254.png?resize=300%2C254" alt="Figure 27" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-27.png?resize=300%2C254 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-27.png?w=990 990w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][27]

Click Next:

[<img class="alignnone size-medium wp-image-1272" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-28-300x263.png?resize=300%2C263" alt="Figure 28" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-28.png?resize=300%2C263 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-28.png?w=988 988w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][28]

Enter the name of the Event Listener that you created in Part III in the Listener port field and click Next:

[<img class="alignnone size-medium wp-image-1274" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-29-300x257.png?resize=300%2C257" alt="Figure 29" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-29.png?resize=300%2C257 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-29.png?w=1007 1007w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][29]

Click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb61.png?resize=555%2C484" alt="image" border="0" data-recalc-dims="1" />][30]

Click Continue:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb62.png?resize=551%2C333" alt="image" border="0" data-recalc-dims="1" />][31]

Click Next:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb63.png?resize=550%2C484" alt="image" border="0" data-recalc-dims="1" />][32]

Provide a unique Context Root name. You cannot accept the default, as the default is already being used but the existing IBM\_WBM\_EMITTER_SERVICES application that came installed with the product. Click Next:

[<img class="alignnone size-medium wp-image-1275" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-33-300x257.png?resize=300%2C257" alt="Figure 33" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-33.png?resize=300%2C257 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-33.png?w=990 990w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][33]

Accept the defaults for Step 10 – 16 by clicking Next.

Click Finish on Step 16:

[<img style="display: inline; border-width: 0px;" title="image" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image_thumb65.png?resize=566%2C484" alt="image" border="0" data-recalc-dims="1" />][34]

Look for the successful installation of the application and click Save:

[<img class="alignnone size-medium wp-image-1278" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-35-300x67.png?resize=300%2C67" alt="Figure 35" srcset="https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-35.png?resize=300%2C67 300w, https://i0.wp.com/sethgagnon.com/wp-content/uploads/2014/06/Figure-35.png?w=652 652w" sizes="(max-width: 300px) 100vw, 300px" data-recalc-dims="1" />][35]

&nbsp;

After your save your changes, at a minimum restart your Support cluster application servers. You can restart the whole environment to have a fresh clean restart.

You should now be able to place events onto your MQ queue and Business Monitor will pull those messages off the queue and consume them. You will need to ensure that the Event Listener you created is up and running and also the MDB application is up and running.

 [1]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image32.png
 [2]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image33.png
 [3]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-3-e1402509631299.png
 [4]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image35.png
 [5]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-5.png
 [6]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-6.png
 [7]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image38.png
 [8]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image39.png
 [9]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-9.png
 [10]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image41.png
 [11]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image42.png
 [12]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image43.png
 [13]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-13.png
 [14]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image45.png
 [15]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-15.png
 [16]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-16.png
 [17]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image48.png
 [18]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-18.png
 [19]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image50.png
 [20]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image51.png
 [21]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image52.png
 [22]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image53.png
 [23]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image54.png
 [24]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image55.png
 [25]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image56.png
 [26]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image57.png
 [27]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-27.png
 [28]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-28.png
 [29]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-29.png
 [30]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image61.png
 [31]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image62.png
 [32]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image63.png
 [33]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-33.png
 [34]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/image65.png
 [35]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2014/06/Figure-35.png