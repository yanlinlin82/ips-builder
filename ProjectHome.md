I' d like to share with all, this script made by me based on root0.net
script for ips instalation.<br>
This script was tested on fedora 9 but it should work in fedora 10 too.<br>
You need 3 network interfaces (One for management and two for the bridge)<br>
Apache and Mysql<br>

When the script finish his execution you will have an IPS with the<br>
following description:<br>
Detection engine:<br>
-Snort<br>
-Easy Update of rules using oinkmaster.pl (just run sh /sbin/oink)<br>
Blocking method (interact with IPtables):<br>
-Quarentine<br>
-Reset Layer 2<br>
-Replace<br>
How is connected?<br>
-It works as an ethernet bridge using brctl in two interfaces to do it.<br>
-This have a management interface.<br>
Alert Mangement:<br>
-BASE (Logged in mysql)<br>
-Syslog (optional)<br>
System Management:<br>
-Webmin (only from localhost)<br>
-SSH (only in management interface)<br>
Extra<br>
-Startup scripts<br>
-Rule Configuration script (iptsamconf.sh) //this was downloaded from<br>
<a href='http://www.root0.net/'>http://www.root0.net/</a><br>
It works greate protecting virtual machines<br>
When you config the vmware interfaces for example put one of the NIC<br>
of the bridge in VMNET7 and  the other must be set as a bridged<br>
In the next step you must connect all the vmware machines that you<br>
want protect connected to VMNET7<br>
Thats it. All machines in vmnet7 will pass throw the bridge to reach<br>
the real network and the trafic will be analized by snort.<br>
<br>
To do<br>
-Daily reports by mail<br>
-Will detect attacks over SSL<br>
-Rule Configuration interface<br>
-Thats it.<br>