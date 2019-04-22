---
layout: post
title:  "Jenkins with Apache reverse-proxy // 'Your proxy setup is broken - Manage Jenkins'"
date:   2019-04-22 19:28 -0500
categories: blog update jenkins
---

So you've setup your Jenkins lab... setup an Apache reverse-proxy out front, but when you login
to Jenkins, it tells you that "Your proxy setup is broken". For me, it was an easy fix... during setup,
I had put the 'Jenkins URL' to the IP of the cloud server I was using. Post setup, I logged in to Jenkins,
went to "Manage Jenkins" section, and scroll down to the "Jenkins Location". Change whatever you have set
there to the URL you are using now. (In my case, from https://my.cloudserver.ip:8080 to https://project.interestedin.info.)
