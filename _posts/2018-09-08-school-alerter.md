---
layout: default
tags: js
title: "school-alerter"
---
# School-alerter
[school-alerter](https://github.com/nicohman/school-alerter) automatically texts me each morning what time I have to be at school that day. I wrote this because I need to be at school at a specific time that changes every day, dependinng onn thinnks like block day scheduling, assemblies or other schedule changes. I actually wrote this after I was late for class one day due to not knowing that there was an assembly, causing the class lengths to be slightly shorter. It works by scraping the RSS feed of my school's Trumba calender, and then categorizes that into a schedules-affecting event. If nothing shows up, it reverts to the default for that school day. It sends me a text message using Twilio(the trial version, of course), and I run it every day at 6:30 using a cron entry on my home server.

# Setup
It'll be a bit involved to set it up if you want to use it yourself, but you'll basically need two files: a schedule, an example of which is available [here](https://github.com/nicohman/school-alerter/blob/master/schedules/cedarcrest.json). You'll also need a file named config.json, with the following values:

- acs: Twilio Account ID
- at: Twilio API key
- numbers: An array of numbers to send the texts to
- from: The twilio number to send from
- name: The name you want to be called in the texts
- sched: The name of the schedule file you want to use; IE, mine is 'cedarcrest'.

Just run that once everyday and you're good!
