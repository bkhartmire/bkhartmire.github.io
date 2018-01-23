---
layout: post
title:      "Fixing an 'Address Already in Use' Error"
date:       2018-01-23 13:58:40 -0500
permalink:  enter_your_title_here
---


This is a simple fix, so don’t despair! I started facing the issue that often when I’d try to start my rails server I’d receive the following error:

`initialize': Address already in use - bind(2) for "0.0.0.0" port 3000 (Errno::EADDRINUSE)

Simply run the following command in your terminal to figure out what oth4er processes are currently running:

 	$ lsof –wni tcp:3000

In this case, 3000 is my port. Your output will probably look something like this:


![Imgur](https://i.imgur.com/lcta3tx.png)


See that PID column? Those are the Process IDs where your port is already in use. To kill them simply run kill -9 PID for each process listed:
	
	$ kill -9 15315
	$ kill -9 15316

Now try running the server again. The issue should be resolved!

