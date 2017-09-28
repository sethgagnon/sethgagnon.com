---
title: Integration Designer 7.5 Could Cause Your User Account to be Locked Out
author: Seth
type: post
date: 2012-05-17T17:20:55+00:00
url: /integration-designer-7-5-could-cause-your-user-account-to-be-locked-out/
jabber_published:
  - 1337275257
email_notification:
  - 1337275260
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"203173298891259904";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150954034359919";}}}'
categories:
  - Integration Designer

---
Are you suddenly experiencing frequent lockouts of your user account after you have recently changed your password? One important thing to note is that IBM Integration Designer does store the user ID and password that you initially set up to use with the servers that you created.  As you can see in the image below and by double clicking on the server that you have configured in your local test environment (or any other servers for that matter), IID stores the username and password for how it connects to Process Center and your servers.

[<img class="alignnone size-full wp-image-150" title="iidloackout" src="https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png?resize=600%2C363" alt="" srcset="https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png?w=1280 1280w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png?resize=300%2C181 300w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png?resize=1024%2C620 1024w, https://i2.wp.com/sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png?resize=494%2C300 494w" sizes="(max-width: 600px) 100vw, 600px" data-recalc-dims="1" />][1]

<!--more-->

What can happen here if you use your own user account is that IID will store the credentials your first provided when you set this server up.  When you change your password for your user account, this will update in your LDAP or Active Directory; however, IID will repeatedly try to connect using your old credentials, ignoring any authentication failures.  So, after the usual three incorrect attempts, or whatever your policy is, the user account will become locked out.  This will continue until you lock you out until you change the credentials here on the Security screen in IID for the configured servers you have in place.

Ideally, IID should not be retrying the connection after it receives an authentication failure and it should prompt you for you new password.  Yet, at this time, the product does not have that capability.  So, there are two options that IBM provides: 1) Use a service ID with a non-expiring password for these servers, or 2) Modify the field in this properties screen for the server status interval (default is 5000 msec). If you increase this number to a much larger number, the user will have time to come into IID and change their credentials before the account becomes locked out again.

In my opinion, the latter is not really a solution. Actually, neither appear to be a true solution to the problem, but nonetheless, in my experience, I would use another ID other than your own user account.

 [1]: https://i0.wp.com/www.sethgagnon.com/wp-content/uploads/2012/05/iidloackout.png