# Implementing technical security controls on Windows and Kali Linux VM's.

**Technical Control Implementation Details**

**Control number:1**

Type: Detective

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: Code Meter Runtime 6.70

Implementation steps: 
Upgrade to Code Meter Runtime 8.10 as the existing version on the server uses predictable encryption key which can be exploited.
Download the latest Code Meter Runtime application file and install it replacing the older version.

**Control number:2**

Type: Preventative

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: Windows Server Update services

Implementation steps: 
Go to Server Manager and install WSUS server role.
Approve and deploy WSUS updates by using the WSUS Management Console, and configure WSUS to automatically approve installation of updates.

**Control number:3**

Type: Detective

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: Tenable Nessus 8.15.0

Implementation steps: 
Upgrade to Nessus 10.7.4 as the existing version has been affected by multiple Vulnerabilities.
Download the latest version .msi application file from tenable website and install it replacing the existing version.

**Control number:4**

Type: Detective

System: Kali GNU/Linux Rolling, 10.11.9.148, KALI

Application or Service: Open JDK 17.0.8

Implementation steps: 
Upgrade to Open JDK 22.0.1 as the existing version has been affected by multiplevulnerabilities allow unauthenticated attacker with network access via multiple protocols.
Download the latest version .tar file, install it from the terminal, configure and update to the new java version, uninstall the older versions in the system.
              
**Control number:5**

Type: Detective

System: Kali GNU/Linux Rolling, 10.11.9.148, KALI

Application or Service: ClamAV 1.0.1 and ClamTK

Implementation steps: 
 Upgrade to Clam AV 1.0.6 as the existing version has been affected by a vulnerability in the Virus Event feature where the attacker could manipulate and inject malicious code.
 Install the latest version of Clam AV and GUI Clam TK from the terminal. 

**Control number:6**

Type: Preventative

System: Kali GNU/Linux Rolling, 10.11.9.148, KALI

Application or Service: Unattended upgrades

Implementation steps: 
Install Unattended upgrades from the Linux terminal to ensure that important security patches for installed packages are automatically downloaded. 
Choose Yes to automatically download and install stable updates.

**Control number:7**

Type: Detective

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: Microsoft network server-SMB sign

Implementation steps: 
Enforce message signing in the system configuration found in the policy setting, as a remote attacker can conduct man in the middle attacks against the server.
Choose Enabled option for Microsoft network server: Digitally sign communications(Always).
 
**Control number:8**

Type: Preventative

System: Kali GNU/Linux Rolling, 10.11.9.148, KALI

Application or Service: Suricata 7.0.5

Implementation steps: 
Install Suricata and configure the rule set and update with the emerging rules to monitor the network traffic for signs of attacks and threats.

**Control number:9**

Type: Recovery

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: Windows Server Backup

Implementation steps: 
Install Windows Server Backup using power shell.
Configure a backup schedule for required data to backup and store in a secure location.
         
**Control number:10**

Type: Detective

System: Kali GNU/Linux Rolling, 10.11.9.148, KALI

Application or Service: Apache Log4j 2.14.0

Implementation steps: 
Upgrade to Apache Log4j 2.17.1 as the existing version has been affected by a RCE vulnerability, where a remote attacker can execute arbitrary commands.
Download the latest version of Apache Log4j, edit the pom.xml file and add log 4j dependency, run mvn install command for the version to be updated.

**Control number:11**

Type: Preventative

System: Microsoft Windows Server 2019 Datacenter, 10.11.9.149, WINDOWS

Application or Service: AuditTAP Release 5.9.0

Implementation steps: 
Download and install AuditTAP.
Copy module folders into module path, import the modules and install the modules.

**Test and Evaluation Findings**

**Control number:1**
Test outcomes: After updating the code meter runtime application to the latest version, launched Nessus network scan once again and the vulnerability was fixed.
Before the patch:

![image](https://github.com/user-attachments/assets/18bcae19-e847-496d-bb70-e67b9b6e5cb7)

After the patch:

![image](https://github.com/user-attachments/assets/ebb27fab-2e87-4e7a-8e6f-c6c2a3bc4e38)

**Control number:2**
Test outcomes: Windows Server Update services was installed and configured for installing automatic updates which will secure server from vulnerabilities. 

![image](https://github.com/user-attachments/assets/b637f9d4-8526-4ecc-809a-684cd7a71eb9)

**Control number:3**
Test outcomes: After updating the Nessus to the latest version, launched Nessus network scan once again and the vulnerability was fixed.

Before and after updates:

![image](https://github.com/user-attachments/assets/0bb40a97-72b8-4796-8cf7-79266ed38923)

![image](https://github.com/user-attachments/assets/3c0f441f-ea7a-47c7-a922-93f58d5fb50e)

![image](https://github.com/user-attachments/assets/f665b8eb-4eae-4c66-a997-25cc17aa95c2)

**Control number:4**
Test outcomes: The current choice of Java version is the latest installed one and the OpenJDK vulnerability was fixed. 
Before and after updates:

![image](https://github.com/user-attachments/assets/4600d377-9abc-401c-916d-aa38469d4b3c)

![image](https://github.com/user-attachments/assets/276ea3dd-a7e4-4798-8a01-7df3c4dcd967)

**Control number:5**
Test outcomes: Clam AV version was updated, was running successfully and the vulnerability was fixed in the vulnerability scan.
Before and after updates:

![image](https://github.com/user-attachments/assets/80bfec8e-23a1-424b-8842-0af137b53cfa)

![image](https://github.com/user-attachments/assets/39130243-e25d-48f2-ac86-60a554c3be6d)

![image](https://github.com/user-attachments/assets/90c20041-7187-4f53-bb9b-413bf9d957eb)

![image](https://github.com/user-attachments/assets/b1990a94-9353-4b03-a8bd-28d98ca89340)

![image](https://github.com/user-attachments/assets/8fb12702-6528-4431-bc04-3bcbe8bf4ac6)

**Control number:6**
Test outcomes: Unattended upgrades status was actively running on the Linux server.
![image](https://github.com/user-attachments/assets/58345ddc-9233-4691-bbf4-cbfc6cba9d96)

![image](https://github.com/user-attachments/assets/857a6e21-a719-42f4-a5c5-c31b4c8f5277)

**Control number:7**
Test outcomes: SMB signing not required vulnerability was fixed.
Before and after updates:

![image](https://github.com/user-attachments/assets/0fc528e4-d350-4f19-9754-8d0f24af9263)

![image](https://github.com/user-attachments/assets/cc823b61-0dfa-4c60-b212-cc481825f7e0)

![image](https://github.com/user-attachments/assets/4d7f8416-8307-4e0b-87bb-82ff584cd644)

**Control number:8**
Test outcomes: Suricata was installed, configured and actively running on the server.

![image](https://github.com/user-attachments/assets/7e9492d8-9df6-4cff-895d-f7bbe8b069bb)

![image](https://github.com/user-attachments/assets/a46870b1-8aa7-4e75-b16c-127bc0b6e5a6)

![image](https://github.com/user-attachments/assets/3c0dc8a0-fea6-4b7b-8db5-123b07b8d85e)

**Control number:9**
Test outcomes: Windows backup server was installed, backup schedule was configured and ready to back up the selected data. 

![image](https://github.com/user-attachments/assets/75a21b2e-6510-4440-8030-233ce7ab7339)

**Control number:10**
Test outcomes: Apache log4j is updated and RCE vulnerability was resolved in the vulnerability scan.
Before and after updates:

![image](https://github.com/user-attachments/assets/86d15c2b-7962-4b6c-9368-cfd3249c9259)

![image](https://github.com/user-attachments/assets/bd72f4ee-1245-4248-8a85-c3ca614e936c)

**Control number:11**
Test outcomes: Security hardening report was generated.

![image](https://github.com/user-attachments/assets/d12255b9-02d4-4b95-ad0d-2d9503fa9e52)

![image](https://github.com/user-attachments/assets/a0e80ef5-0c15-4cc1-8ab6-8b3d16f5cd24)

![image](https://github.com/user-attachments/assets/6b8f8f20-6981-4b19-8379-bd46b506cf27)

![image](https://github.com/user-attachments/assets/5dc2f420-1cab-480c-8c8c-7e32162e4888)

**Windows server vulnerability scan report before security controls implementation:**

![image](https://github.com/user-attachments/assets/23369a5e-6027-4568-9c00-26b0ef32985b)

**Windows server vulnerability scan report after security controls implementation:**

![image](https://github.com/user-attachments/assets/c3859a12-3cfd-4dd0-8c15-0034e1a81730)

**Linux server vulnerability scan report before security controls implementation:**

![image](https://github.com/user-attachments/assets/c643b77a-bf57-4101-a38d-6005950bdf95)

Linux server vulnerability scan report after security controls implementation:

![image](https://github.com/user-attachments/assets/e6aaac22-2a8e-4e69-b094-125e693a1edc)

 Conclusion:Implementing automatic update services will resolve such vulnerabilities and enhance the protection. Network based IDS/IPS solution must be employed to detect and preventthreats. A backup strategy plan must be implemented to recover the lost data in case of any cyber-attacks. 




























