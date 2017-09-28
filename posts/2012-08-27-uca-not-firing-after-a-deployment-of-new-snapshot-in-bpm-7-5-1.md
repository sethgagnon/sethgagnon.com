---
title: UCA Not Firing After a Deployment of New Snapshot in BPM 7.5.1?
author: Seth
type: post
date: 2012-08-27T16:12:34+00:00
url: /uca-not-firing-after-a-deployment-of-new-snapshot-in-bpm-7-5-1/
kalinsPDFMeta:
  - '{"showLink":"default"}'
categories:
  - BPM Application Issues

---
After deploying a new snapshot to your BPM 7.5.1 Process Server environment, are you noticing that your Undercover Agent (UCA) is not firing on your set schedule? I noticed this after deploying an application that uses a scheduler event and it should fire at certain times that were decided upon by the development team. I first noticed this be checking in the BPM Process Admin console:

[<img class="alignnone size-large wp-image-970" title="process admin" alt="" src="https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/process-admin-1024x617.png?resize=600%2C361" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/process-admin.png?resize=1024%2C617 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/process-admin.png?resize=300%2C180 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/09/process-admin.png?w=1284 1284w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][1]

<!--more-->

Here, the Event Manager Monitor shows you the scheduled events. If you notice that the schedule is not correct, as per what the developer set in the application in Process Designer, you can actually change these value in the BPM database (BPMDB).  There is a table called LWS\_EM\_TASK, where you can edit the scheduled times and the repeating schedule:

[<img class="alignnone size-large wp-image-934" title="LSW_EM_TASK" alt="" src="https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/08/LSW_EM_TASK-1024x610.png?resize=600%2C357" srcset="https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/08/LSW_EM_TASK.png?resize=1024%2C610 1024w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/08/LSW_EM_TASK.png?resize=300%2C178 300w, https://i1.wp.com/sethgagnon.com/wp-content/uploads/2012/08/LSW_EM_TASK.png?w=1052 1052w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][2]

After you commit the changes to the database, you can then log back into BPM Process Admin and view the changes you made in the Event Manager Monitor. The UCA should then kick off at the next scheduled time that you scheduled for.

 [1]: https://i1.wp.com/www.sethgagnon.com/wp-content/uploads/2012/09/process-admin.png
 [2]: https://i2.wp.com/www.sethgagnon.com/wp-content/uploads/2012/08/LSW_EM_TASK.png