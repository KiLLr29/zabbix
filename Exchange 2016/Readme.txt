In order to use this template.

Import this template file into Zabbix.
Zabbix must be 4.4.x or higher for this to work.

This template is based on using the {EVENT.TAGS} as a execute command within Actions.
(Note: The whole Trigger will execute all alerts and do with them as you specify but independently execute based on 5m runtimes)
So if there are three (3) services out, it may take fifteen (15) to twenty (20) mins to restart them.


To create an "ACTION" do the following.

Add "All Services" and tag them as (Trigger equals XXX)

See Example: Trigger equals Template Microsoft Exchange Server 2016 - Services: Service: MSExchangeUMCR on Template Microsoft Exchange Server 2016 - Services

If done correctly, you will have A~AE Trigger equals, about (31 Objects)

Once done, under "Operations" to Execute a command on the windows server use the following configuration.

Operation Type: Remote Command (Note: Zabbix Agent must be set to "Allow Remote Commands)
Target list: Current Host
Type: Custom Script
Execute on: Zabbix Agent
Commands: net start {EVENT.TAGS}

Yes, it a "Vague" tortural (Sorry) but i'm lazy... Zzz... Zzzz..
