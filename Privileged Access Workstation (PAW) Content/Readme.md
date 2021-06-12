*Original text from Technet Gallery.*

------------


We have finally published a corrected pawfirewall.wfw!  Thanks for your patience as we worked through that - we needed to test for a very specific issue (not the domain trust one), but at this point we're confident it has been resolved.

**Most recent update** - 02/05/2018 - Added updated pawfirewall.wfw (entitled pawfirewallupdate.wfw to distinguish from the previous version)
**Previous update** - 03/23/2017 - Removed pawfirewall.wfw while we resolve an issue with domain trusts 

These scripts and files are used in the Privileged Access Workstation (PAW) instructions published at http://aka.ms/cyberpaw.
This .zip file includes the following files:

- ADEnvironment.ps1 - function library for the Active Directory preparation scripts
- Create-PAWGroups.ps1 - script to create the appropriate security groups in Active Directory using Groups.csv as a master list
- Create-PAWOUs.ps1 - script to create the appropriate organizational units in Active Directory
- Groups.csv - master list of required groups
pawfirewallupdate.wfw - Windows Firewall configuration file with all appropriate rules and exclusions for PAWs (updated 01/18/2018) 

> NOTE: This sample WFW provides allows only the most minimal set of network connectivity (enough to log onto the PAW itself).  You will need to modify the ruleset to allow outbound network access from the PAW to network resources (e.g. Remote Desktop, Remote PowerShell, Microsoft Management Console, etc.).NOTE: This sample WFW provides allows only the most minimal set of network connectivity (enough to log onto the PAW itself).  You will need to modify the ruleset to allow outbound network access from the PAW to network resources (e.g. Remote Desktop, Remote PowerShell, Microsoft Management Console, etc.).

- proxy.pac - Internet Explorer/Microsoft Edge proxy configuration file
- ProxyBypassList.txt - text file of allowed properties for use in populating proxy bypass list in Internet Explorer/Edge (updated 01/31/2017) 

> NOTE: Bypass URLs are automatically assigned to the Local Intranet Zone.  If you deploy Bypass URLs, consider increasing the security level of the Local Intranet Zone from the default of Medium-Low to either Medium or Medium-HighNOTE: Bypass URLs are automatically assigned to the Local Intranet Zone.  If you deploy Bypass URLs, consider increasing the security level of the Local Intranet Zone from the default of Medium-Low to either Medium or Medium-High

- Set-PAWOUDelegation.ps1 - script to delegate permissions within Active Directory to the groups created by Create-PAWGroups.ps1
- UserProxySettings.adm - Group Policy template to allow for centralized control and deployment of proxy bypass list 

PAWs provide a dedicated operating system for sensitive tasks that is protected from Internet attacks and threat vectors. Separating these sensitive tasks and accounts from the daily use workstations and devices provides very strong protection from phishing attacks, application and OS vulnerabilities, various impersonation attacks, and credential theft attacks such as keystroke logging, Pass-the-Hash, and Pass-The-Ticket.   
