---
title: Issues with WebSphere Service Registry and Repository Promotion
author: Seth
type: post
date: 2012-04-13T15:23:23+00:00
url: /issues-with-websphere-service-registry-and-repository-promotion-corba-transaction_rolledback/
jabber_published:
  - 1334330606
publicize_results:
  - 'a:2:{s:7:"twitter";a:1:{i:223852360;a:2:{s:7:"user_id";s:10:"sethgagnon";s:7:"post_id";s:18:"190822526824361984";}}s:2:"fb";a:1:{i:585439918;a:2:{s:7:"user_id";s:9:"585439918";s:7:"post_id";s:17:"10150786447409919";}}}'
categories:
  - WebSphere Service Registry Repository
tags:
  - service registry
  - websphere
  - wsrr
  - wsrr promotion

---
Are you seeing this error (or something very similar) in your WebSphere Service Registry and Repository log file while trying to promote artifacts:

`org.omg.CORBA.TRANSACTION_ROLLEDBACK vmcid: 0x49421000 minor code: 4``4 completed: Maybe`

`<!--more-->`

`It could be that your request if failing due to an ORB timeout. The default value of the ORB timeout is 180 seconds, but depending on your configuration and the size of the artifacts, it may be necessary to increase the timeout.`

`Try bumping up the ORB timeout to 380 seconds and then retesting the same promotion activity again. You can change the ORB timeout setting in the WebSphere Admin Console here:`

`Application Servers > server-name > Container Settings > Container Services > ORB Service`

`You will need to perform this change from your Governance WSRR environment and the connected environment receiving the promotion. After the change, restart the application servers and try to perform the same promotion again. Adjust timeout setting accordingly.`