---
layout: post
title:  "Read only logseq"
date:   2024-03-04 00:00:00 +0900
categories: logseq
---
This is guide to have "view only mode" for Logseq that runs in the web.

Logseq has a [demo site](https://demo.logseq.com/). However, several button presses are required to use this site.

![Step 1](/assets/2024-03-04-Read-Only-Logseq/1.png){:style="display:block; margin-left:auto; margin-right:auto"}

![Step 2](/assets/2024-03-04-Read-Only-Logseq/2.png){:style="display:block; margin-left:auto; margin-right:auto"}

![Step 3](/assets/2024-03-04-Read-Only-Logseq/3.png){:style="display:block; margin-left:auto; margin-right:auto"}

![Step 4](/assets/2024-03-04-Read-Only-Logseq/4.png){:style="display:block; margin-left:auto; margin-right:auto"}

A functioning "view only mode" should automatically click on these buttons. 

Since Logseq does not seem too interested in making a functioning webapp, I've written a [Tampermonkey](https://tampermonkey.net/) script to do this. 

This is a tampermonkey script to automatically click these buttons, and to disable mouse and keyboard input to achieve view only mode.

<script src="https://gist.github.com/yuyangchee98/1dc49651895b9d4086c8e5622b56911b.js"></script>

Personally, I use this as a new tab page, allowing a quick glance at your Logseq journal every time a new tab is opened.