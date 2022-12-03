#security_driven_networking
__SECURITY DRIVEN NETWORKING overview__
provides secure high performance connectivity between users,applications,devices.
uses- internal segmentation/automated threat protection/policy enforcement

what is digital transformation
the process of using digital technologies to create new or to modify existing organizational processes,culture and customer experiences to meet changing requirements.
benefits are enhances the collection of customer data/uses resources more efficiently. 

digital transformation creates many network edges inconsistent security, unpredictable experience, complex to manage.

__FORTIGATE__
ngfw - next generation firewall
powered by fortios
root fortigate is in edge.
can see access points, endpoints, threats, on premise and SaaS applications.
FORTIGATE advanced NGFW functions
application control(to create policies), intrusion prevention, antivirus, URL filtering, sandboxing, SSL inspection
spu - security process units(fortigate devices powered by spu)
SD-WAN is built into fortigate and can be enabled- application steering(block unathorized applications), wan path remediation(optimizing bandwidth), ipsec VPN
FORTIGATE FORM FACTORS- physical, VM, firewall as a service
FortiManager - centrally manages security fabric devices like fortigate. provide centralized policy enforcement. 

__FORTIAP__
fortiap is a secure access point device designed and produced by fortinet that allows users to access the network using wifi technologies.
secure LAN edge.
fortinet secure lan edge through fortilink
fortiwlm - troubleshooting, wireless management.
fortideploy - deploy fortiap, fortiAP connects to fortiDeploy/ fortiap direct to fotigate.

__FORTIMANAGER__
fortimanager is a device either physical or virtual provides single console to administrator and gain visibility to fortinet devices
fabric management center- enable customers to simplify the network operations.
	simplified provisioning- 
	centralized management-
	network analytics -
	compliance reporting-
	network automation-

__FORTISWITCH__
fortiswitch is a secure network switch which is designed by fortinet
fortiwsitch deployment options - fortilink/ standalone
fortinet secure ethernet through fortilink
fortilink enables fortigate to extend its NGFW features into wired and wireless network component. 
fortilink connects fortigate and fortiswitch, fortiapi is connected to fortiswitch
fortiswithc product
	access switch family
	data center switch family
	fortiswitch rugged
cloud management for fortiswitch
	fortiswitch cloud- manage stand alone fortiswitch deployment
	fortigate cloud- manage fortilink enabled fortiswitch deployment

__FORTISASE__
__FORTIEXTENDER__ - integrating 5G LTE(long term evolution) connections into sd-wan

#Zero_trush_access
fortinet zta
principles of the fortinet ZTA
	verify
	give minimal access
	assume that the network is compromised
reducing attack surface

__forticlient EMS__ endpoint management server.(use zero trush tagging rules)
__Fortinet fabric management center__
	fortimonitor
	forti analyzer
	forti siem
	forti soar
	forti EDR
	forti AI



