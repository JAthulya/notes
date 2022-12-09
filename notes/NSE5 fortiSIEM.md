noc - network performance availabilty and uptime.
soc - network security and compliante

___SIEM___
real time asset and configuration discovery
-aware of what is attached to the network
-able to collect event and log data from all relevant elements.
only tool has self learning, real time, asset discovery and device configuration 
discovery information is stored in the configuration management database(CMDB)- identifies network devices like routes

___FortiSIEM analytics___

___Group by data aggregation___

___rules and mitre attack___
sub pattern for a rule is filter / aggregate / group by
third step set the action critiria to the rule.

___incidents___
incident tab- mitre attack view
	rule coverage
	incident coverage
	incident explorer

___reports and dashboards___
fortisiem doesn't allow u to delete system reports.
system dashboards
	summary dashboard
	widget dashboard
	business service dashboard
	pci logging status dashboard
	interface usage 
	identity and location dashboard
cmdb reports can generate in XML format.

___maintaing and tuning___
if its exclamation fortisiem can't reach the device
process selection
	critical- process monitor for up/down
	monitor - process monitor for performance metrics

___troubleshooting___
phoenix.log - shows device discovery logs.
snmpwalk/tcpdump
telnet
fotriSIEM uses expect scripts
./getCmdOutViaSSH.exp
checkWMIMonitorability
wmic - for testing WMI permissions and access
phLicenseTool --show - show the fortisiem license
route add/route del - temporary routes commands
phshowVersion.sh - gathering system info
phstatus- viewing system services status
date- check the time set
service httpd restart - restart the httpd
phxct1 start|stop|reboot - clean stop,start or reboot
shutdown -h now - shutdown the fortisiem
get-fsm-health.py - health check scripts
AOLogs.tar - back end logs
