Alright, I've wasted a *PERFECTLY GOOD WEEKEND FOR EVERYONE!*

This works with Exchange 2016 CU12 or Higher (Or will it?)

OK, this template uses the following:

1: Zabbix Agent Active
2: Triggers
3: Graphs
4: Powershell Script
5: ALERTS (Easly Configerable for EVERYONE ~YEAH!~
6: My Insanity on bad PS1 file scripting

Okay...

Dump these 3 lines of code into the zabbix agent config at teh bottom of "zabbix_agentd.conf". File is located located under C:\Program Files\Zabbix Agent ~NORMALL~ unless you made a diffrent path.... */sigh/*

3 lines of Code Below....
UserParameter=exchange.host[*],powershell -NoProfile -ExecutionPolicy Bypass -File "C:\Program Files\Zabbix Agent\scripts\Mailboxes.ps1" -ActionType "$1" -Key "$2" -Value "$3"

UnsafeUserParameters=1

Timeout=30

Now for the fun part.....

Make a file in your zabbix agent folder called "scripts" ~I can't stress how darn important it is to follow my directions!~

Upload the "Mailboxes.ps1" file into the newly created (Or Old Existing) file called "scripts"

Next *Restart* teh Zabbix Agent Service *MANUALLY* or be lazy and run ~Windows + R~ the type "net stop "Zabbix Agent" then type "net start "Zabbix Agent" - If teh Zabbix Agent failed to start, you have a problem in your config - Don't blame me for that!

Now the ~FUN~ part!

Download the "Microsoft Exchange Server 2016 - Mailboxes.xml" Template and "Import it into zabbix.

Then watch the ~MAGIC~ happen!
