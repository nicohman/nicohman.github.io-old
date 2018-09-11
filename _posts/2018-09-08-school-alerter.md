---
layout: default
tags: js
title: "school-alerter"
---
# School-alerter
[school-alerter](https://github.com/nicohman/school-alerter) automatically texts me each morning what time I have to be at school that day. I wrote this because I need to be at school at a specific time that changes every day, dependinng onn thinnks like block day scheduling, assemblies or other schedule changes. I actually wrote this after I was late for class one day due to not knowing that there was an assembly, causing the class lengths to be slightly shorter. It works by scraping the RSS feed of my school's Trumba calender, and then categorizes that into a schedules-affecting event. If nothing shows up, it reverts to the default for that school day. It sends me a text message using Twilio(the trial version, of course), and I run it every day at 6:30 using a cron entry on my home server.
