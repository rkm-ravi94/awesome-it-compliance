## PCI DSS

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Coding Practices
│   │   ├── Input Validation (e.g., SQL Injection, XSS prevention)
│   │   └── OWASP Top 10 Vulnerabilities
|		└──  Evidences
|		└── Tools 
|			└── SCA
|				└── SonarQube
|				└── GoSec ( golang )
|				└── Owasp Dependency Check
|				└── Snyk
|			└── SAST
|				└── SonarQube
|				└── VeraCode
|				└── SemGrep
|				└── AiKido
|				└── CheckMarx
|				└── Contrast Security
|
│   ├── Encryption of Cardholder Data
│   │   └── TLS/SSL for data in transit, AES-256 for data at rest
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Secure Authentication and Session Management
│   │   └── Multi-Factor Authentication (MFA) for critical applications
|		└──  Evidences
|		└── Tools
|			└── MFA ( Google Auth )
|			└── KeyCloak
|			└── OpenIAM
|			└── OpenLDAP 
|			└── FreeIPA
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Secure Development Lifecycle (SDLC)
│   │   └── Code reviews, Penetration Testing, and Automated Security Scans
|		└──  Evidences
| 		└── Pentest Tools
|			└── Metasploit ( network )
|			└── Aircrack-NG
|			└──  Kismet
|			└── Wifite
|		└── WebApp
|			└── SQLMap
|			└── Burpsuite
|			└── Wfuzz 
|		└── Access Control
|			└── Hydra
|			└── John the reaper
|			└── Medusa
|			└── LDAPSearch
|		└── Data
|			└── SSLyze
|			└── TestSSL
|			└── GNuPG
|		└── Mobile
|			└── MobSF
|			└── Drozer
|
│   └── Application Penetration Testing
│       └── Regular internal/external tests on web/mobile apps
|		└──  Evidences
| 		└── Pentest Tools
|			└── Metasploit ( network )
|			└── Aircrack-NG
|			└──  Kismet
|			└── Wifite
|		└── WebApp
|			└── SQLMap
|			└── Burpsuite
|			└── Wfuzz 
|		└── Access Control
|			└── Hydra
|			└── John the reaper
|			└── Medusa
|			└── LDAPSearch
|		└── Data
|			└── SSLyze
|			└── TestSSL
|			└── GNuPG
|		└── Mobile
|			└── MobSF
|			└── Drozer
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Authentication
│   │   └── Implement Role-Based Access Control (RBAC), MFA
|	|	└──  Evidences
|		└── Tools
|			└── MFA ( Google Auth )
|			└── KeyCloak
|			└── OpenIAM
|			└── OpenLDAP 
|			└── FreeIPA
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Incident Response Plan
│   │   └── Data breach handling and incident management policies
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Backup and Disaster Recovery
│   │   ├── Secure, encrypted backups of cardholder data
│   │   └── Regular testing of recovery processes
|	|	└──  Evidences
|		└── Tools
|			└── BorgBackup (Borg) 
|			└── Restic
|			└── Duplicity
|			└── Amanda (Advanced Maryland Automatic Network Disk Archiver)
|			└── Rclone
|			└── Rsnapshot
|			└── Velero (for Kubernetes backups)
|			└── Bacula
|			└── Snapshots ( Disk, DB Instances ) Cloud Native
|
│   ├── Physical Security Controls
│   │   └── Data center security (e.g., CCTV, biometrics)
|		└──  Evidences
|		└── Tools
|			└── Thales Luna HSM devices ( Physical Server Vault )
|			└── ZoneMinder/Motion (for video surveillance)
│			└── Security Onion/Nagios/MeshCentral ( for monitoring based on Sensors )
|
│   └── User Training and Awareness
│       └── Regular employee training on handling cardholder data
|		└──  Evidences
|
│
└── Infrastructure Point of View (Network and System Security)
    ├── IDS/IPS
    │   └── Implement Intrusion Detection/Prevention Systems
    |	|	└──  Evidences
    |		└──	 Tools
	|			└── IDS/IPS
	|				└── Snort + Snoby
	|				└── SuriCata + Snoby
	|				└── Wazuh
	|				└── Zeek
	|				└── SecurityOnion
	|
    ├── File Integrity Monitoring (FIM)
    │   └── Detect unauthorized changes to critical files
    |	|	└──  Evidences
    |		└── Tools ( File Integrity )
	|			└── Wazuh
	|			└── TripWire
	|			└── Aide
	|			└── Samhain
	|			└── Snoopy Logger
	|
    ├── Antivirus/Anti-malware
    │   └── Deploy antivirus on all systems handling cardholder data
    |	|	└──  Evidences
    |		└──  Tools
    |			 └── ClamAV/ClamWin
    |			 └── Chkrootkit
    |			 └── Rootkit Hunter
    |			 └── Sophos
	├── Vulnerability and Patch Management
	│   └── Regularly scan for vulnerabilities and apply security patches to 	reduce risks.
	|	└──  Evidences
	|	└── Tools
	|		└── Vulnerability_Management_Tools
	|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
	|			└── Image Vulnerability -> Trivy, Grype, Clair
	|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
	|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
	|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
	|
	|		└── Patch_Management_Tools
	|			└── Cloud Native Patch Management System ( AWS, GCP, Azure )
	|			└── Heimdall Patch Management ( 30 days free trial )
	|			└── PDQ Deploy ( windows patch management )
	|			└── Comodo
	|			└── Miradore
	|			└── SCM tools ( Chef, Puppet, Saltstack, Ansible )
	|
    ├── Network Segmentation
    │   └── Isolate cardholder data environments (CDE) from other networks
    |	|	└──  Evidences
    |		└──  Tools
    |			└── DMZ Zone
    |			└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
    |			└── Safeline
    |			└── ModSecurity
    |           └── Shadow Daemon
	|
    ├── Logging and Monitoring
    │   └── Track access and maintain audit logs for at least 1 year
    |	|	└──  Evidences
    |		└── Tools
	|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
	|			└── LOKI ( Prometheus Stack )
	| 			└── GrayLog
	|			└── SigNoz
	|			└── Splunk ( prebuilt filters )
	|
    ├── Encryption (Data at rest and in transit)
	    └── Encrypt cardholder data using AES-256, TLS/SSL for network transmissions
    |	|	└──  Evidences
	|		└──	 Tools
	|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
	|			└── Libgcrypt ( for customer managed encryption )
	|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
	|			└── GnuTLS ( mTLS based comms )
	|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
	|
    └── Other Perspectives
	    ├── Legal and Compliance
		│   ├── Ensure compliance with data protection regulations using CIS security controls.
	    │   └── Maintain documentation for audits and regulatory compliance.
    	|	└──  Evidences
		|
	    ├── HR and Employee Training
	    │   ├── Implement ongoing security awareness training 
	    │   └── Ensure employees are trained on secure handling of sensitive information and access management.
    	|	└──  Evidences
		|
	    └── Management and Leadership
	        ├── Align organizational security policies with PCI DSS Controls to reduce risks
	        ├── Monitor and assess security control effectiveness regularly
	        └── Promote a culture of cybersecurity awareness and proactive threat management
    		└──  Evidences
```

### Checklist

* https://www.rsisecurity.com/files/PCI-DSS-Checklist-by-RSI-Security.pdf
* https://listings.pcisecuritystandards.org/documents/PCI_DSS-QRG-v3_2_1.pdf
* https://assets.ctfassets.net/e6d9jibdbc6c/5hqtJr0RGTaFN4Pv3bz3o3/87167ff573caf174fac9bf3d2b8e4cc7/VGS_-_PCI_Compliance_Checklist.pdf
* https://listings.pcisecuritystandards.org/documents/PCI-DSS-v3_2_1-ROC-Reporting-Template.pdf
* https://assets.website-files.com/60b6a4471d974075c999d1fb/61771168b644071e34d9baeb_Vanta_PCI_DSS_Compliance_Checklist.pdf


### Policy Documentation Required
-   **Information Security Policy**
-   **Access Control Policy**
-   **Data Encryption Policy**
-   **Incident Response Plan**
-   **Vulnerability Management Policy**
-   **Change Management Policy**
-   **Network Security Policy**
-   **Audit Log and Monitoring Policy**
-   **Third-Party Service Provider Policy**
-   **Password Policy**
-   **Acceptable Use Policy**
-   **Backup and Recovery Policy**
-   **Penetration Testing Policy**


### Helpful Links
-   https://www.pcisecuritystandards.org/document_library
-   https://www.complianceforge.com/pci-dss-documentation
