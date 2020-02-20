---
layout: post
title: GTM multi parameter lookup tables
post_description: blah
excerpt_separator: <!--more-->
---
# Google Tag Manager multi parameter lookup tables

## Worst titled blog ever!

We use a few User Research tools on our website and these are deployed using Google Tag Manager, dead easy. A User Researcher goes in, adds there page to a GTM regex table variable and through the magic, the tool is deployed.
<!--more-->

This is great and I was even capturing the User Researcher who had the tool up!

![Simple regex variable](/images/1-1-gtm.png)

However the team came to me to ask if the deployment rate could be changed on a page by page basis….now that got me scratching my head, how could i do this without requiring the user to duplicate their effort and requiring me to manage duplicate variables.

Well, after much head scratching i worked it out, and here it is in it's glory!

![Multi variable regex](/images/1-2-gtm.png)

By adding several parameters, i can get ALL THE DATA! But how to access it…Via a new 'system' variable that interrogates the first variable.

![Extract the bits you want into new variables](/images/1-3-gtm.png)

So with some nifty regex you can create a new variable for each 'parameter' in the original variable, and these can then be used by a trigger.