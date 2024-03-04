---
layout: post
title:  "Read only logseq"
date:   2024-03-04 00:00:00 +0900
categories: logseq
---
This is guide to have "view only mode" for Logseq that runs in the web.

Logseq has a [demo site](https://demo.logseq.com/). However, several button presses are required to use this site.

![Step 1](assets/2024-03-04-Read-Only-Logseq/1.png)
![Step 2](assets/2024-03-04-Read-Only-Logseq/2.png)
![Step 3](assets/2024-03-04-Read-Only-Logseq/3.png)
![Step 4](assets/2024-03-04-Read-Only-Logseq/4.png)

This is a tampermonkey script to automatically click these buttons, and to disable mouse and keyboard input to achieve view only mode.
		  ```js
		  // ==UserScript==
		  // @name         Logseq view only
		  // @namespace    http://tampermonkey.net/
		  // @version      2024-03-02
		  // @description  view only mode by disabling keyboard and mouse, set as chrome new tab page to always view your logseq journal
		  // @author       You
		  // @match        https://demo.logseq.com/*
		  // @icon         data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==
		  // @require      http://code.jquery.com/jquery-latest.js
		  // ==/UserScript==
		  
		  (function() {
		      'use strict';
		      document.addEventListener("keydown", handler, true);
		  
		      function handler(e) {
		          e.stopPropagation();
		          e.preventDefault();
		      }
		  
		      setTimeout(function() { document.getElementsByClassName('ui__button inline-flex items-center justify-center whitespace-nowrap text-sm gap-1 font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 select-none bg-primary/90 hover:bg-primary/100 active:opacity-90 text-primary-foreground hover:text-primary-foreground as-classic h-7 rounded px-3 py-1 ui__modal-enter')[0].click(); }, 500);
		      setTimeout(function() { document.getElementsByClassName('item group flex items-center p-2 text-sm font-medium rounded-md')[0].click(); }, 700);
		      setTimeout(function() { document.querySelector('[title="Import changes from local files"]').click(); }, 1000);
		      setTimeout(function() { document.getElementsByClassName('ui__button inline-flex items-center justify-center whitespace-nowrap text-sm gap-1 font-medium ring-offset-background transition-colors focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-ring focus-visible:ring-offset-2 disabled:pointer-events-none disabled:opacity-50 select-none bg-primary/90 hover:bg-primary/100 active:opacity-90 text-primary-foreground hover:text-primary-foreground as-classic h-7 rounded px-3 py-1 ui__modal-enter')[0].click(); }, 1200);
		  
		      setTimeout(function() { document.addEventListener("click", handler, true);}, 1500);
		  })();
		  ```

The demo logseq site can then be set as the new tab page, allowing a quick glance at your Logseq journal every time a new tab is opened.