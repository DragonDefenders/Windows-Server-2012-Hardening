# Windows-Server-2012-Hardening
Has link to benchmark page for various systems

2012 Web App.



Hardening
To harden the Windows 2012 Server, you should first use the Security Configuration Wizard. To do this:

Server Manager > Dashboard > Tools > Security Configuration Wizard
In the Wizard select Create a New Security Policy (if one does not already exist)
Optional: View Configuration Database for in-depth information
After clicking next you will select the role the server plays
Ex: If the server is responsible for Web apps, disable things that are not needed for the Web App.

You will be asked about network and registry settings, hit continue unless given specific instructions on what to do.

Audit select Audit successful and unsuccessful actions

Finally Save Policy and decide to apply now or later

Hardening (checklist) *
*There is more that can be done, this is just an overview
Use GPO (For further security policy edits)
Use NTFS Only
-	Format all partitions on server to NTFS
-	Use convert tool to convert FAT partitions to NTFS
Administrator (Through GPO)
-	Change name
-	Use strong password
o	At least 9 characters long
o	1 punctuation mark 
o	Optional: include nonprinting ASCII character
	ASCII characters are ALT + 3 numbers from numeric keypad
Example: ϛ, ʎ, å, ȱ, ỗ, ʍ, η, ˱, σ, ˥, Ł
Disable Guest Account (Through GPO)
Set Account Lockout Policy (Through GPO)
Remove All Unnecessary File Shares
Set Appropriate ACL (Access Control Lists) on All Necessary File Shares (Through GPO)
Install Antivirus Software and Updates

Audit Logons:

To ENABLE Audit Logons follow these steps:

Open GPO (Group Policy Management) > Forest: cybersecurity.local* > Domains > cybersecurity.local* || optional: Right-click on name and select Create GPO in this domain and link it here to create GPO for domain|| > Right-click on created GPO and select Edit > This will open the Group Policy Management Editor 
In GPOE (Group Policy Management Editor > Computer Configurations > Windows Settings > Security Settings > Local Policies > Audit Policy
In Audit Policy** > Double-Click on Audit Account logon events > Define the policies and select Success and Failures > Apply > OK
*This will be your domain name
**For the competition you may consider auditing other things like Policy change, logon events (which differs from ACCOUNT logon events), privilege use, object access, directory service access, etc.
To ACTUALLY SEE the logon attempts follow these steps:
You need to use Event Viewer:

Method 1: Start > Control Panel > System and Maintenance > Administrative Tools > Double-click Event Viewer
Method 2: Open a command prompt > eventvwr
Method 3: Server Manager > Tools > Event Manager
After opening Event Viewer > Windows Logs > Security* > for faster information (if there is a lot) click Task Category and Find the Logon section
*You can also check Application, System, and the other options for other logged events. 
Information:
Benchmarks! Excellent Source:
Has many, many, MANY systems to work with!
https://benchmarks.cisecurity.org/downloads/multiform/index.cfm


Benchmarks, terms, etc.
Windows Server 2012 R2: https://benchmarks.cisecurity.org/tools2/windows/CIS_Microsoft_Windows_Server_2012_R2_Benchmark_v1.0.0.pdf
Windows Server 2012: https://benchmarks.cisecurity.org/tools2/windows/CIS_Microsoft_Windows_Server_2012_Benchmark_v1.0.0.pdf

PORTS: http://www.sbsfaq.com/?p=3730
Windows Guide*: https://technet.microsoft.com/en-us/library/dn383644.aspx
  *additional information
