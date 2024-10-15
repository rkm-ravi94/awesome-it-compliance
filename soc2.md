## SOC 2 (System and Organization Controls 2)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Software Development Lifecycle (SDLC)
│   │   └── Follow secure coding practices to ensure SOC 2 Trust Service Criteria are met.
|	|	└──  Evidences
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
│   ├── Data Integrity and Confidentiality
│   │   └── Ensure applications protect the integrity and confidentiality of data.
|	|	└──  Evidences
|		└── Tools ( File Integrity )
|			└── Wazuh
|			└── TripWire
|			└── Aide
|			└── Samhain
|			└── Snoopy Logger
|	
│   ├── Encryption and Data Protection
│   │   └── Use encryption (TLS/SSL, AES-256) to secure sensitive customer data at rest and in transit.
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|	
│   ├── Vulnerability Management
│   │   └── Regularly scan applications for security vulnerabilities and address them promptly.
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|	
│   └── Access Controls
│       └── Implement role-based access control and ensure secure authentication for applications.
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
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Identity Management
│   │   └── Ensure that only authorized personnel have access to systems processing sensitive data.
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
│   ├── Incident Response and Breach Notification
│   │   └── Implement an incident response plan to address security incidents and breaches.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|	
│   ├── Data Backup and Recovery
│   │   └── Ensure regular and secure backups of data, with recovery procedures in place.
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
│   ├── Continuous Monitoring
│   │   └── Continuously monitor systems for suspicious activities or policy violations.
|	|	└──  Evidences
|		└── Tools
|			└── OpenSCAP
|			└── Wazuh
|			└── Lynis
|			└── Scoutsuite
|			└── Prowler
|			└── Falco
|	
│   └── Change Management
│   |   └── Implement a formal change management process for IT systems.
|	|	└──  Evidences
|		└──  Tools
|			└──  CI/CD Tools for Release Management
|			└── JIRA/Trello/Email/Slack for change management
|			└── GitHub ( ChangeLogs )
|	
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Network Security and Firewalls
│   │   └── Implement secure firewalls and network segmentation to protect sensitive data.
|	|	└──  Evidences
|		└──  Tools
|			 └── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|	
│   ├── Encryption and Key Management
│   │   └── Use strong encryption algorithms for protecting data, and secure key management processes.
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|	
│   ├── Logging and Monitoring
│   │   └── Log access to critical systems and data, and review logs for anomalies.
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|	
│   ├── Intrusion Detection and Prevention (IDS/IPS)
│   │   └── Deploy IDS/IPS systems to monitor network traffic and prevent unauthorized access.
|	|	└──  Evidences
|		└──	 Tools
|			└── IDS/IPS
|				└── Snort + Snoby
|				└── SuriCata + Snoby
|				└── Wazuh
|				└── Zeek
|				└── SecurityOnion
|	
│   └── Vulnerability Scanning and Patching
│       └── Regularly scan for vulnerabilities and apply security patches.
|		└──  Evidences
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
│
├── SOC 2 Trust Service Criteria
│   ├── Security
│   │   └── Implement security controls to protect against unauthorized access.
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
│   ├── Availability
│   │   └── Ensure that systems are available for operation and use as agreed upon.
|	|	└──  Evidences
|	
│   ├── Processing Integrity
│   │   └── Ensure that system processing is complete, accurate, and authorized.
|	|	└──  Evidences
|	
│   ├── Confidentiality
│   │   └── Protect confidential data, especially during storage and transmission.
|	|	└──  Evidences
|	
│   └── Privacy
│       └── Ensure personal data is collected, used, retained, and disclosed in compliance with privacy policies.
|	|	└──  Evidences
|	
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure that privacy and confidentiality requirements are aligned with legal standards.
    │   └── Maintain documentation for audits and SOC 2 reporting.
	|	└──  Evidences
	|	
    ├── HR and Employee Training
    │   ├── Train staff on SOC 2 security policies and procedures
    │   └── Conduct regular security awareness programs focusing on SOC 2 compliance.
	|	└──  Evidences
	|	
    └── Management and Leadership
        ├── Assign leadership to oversee SOC 2 compliance, security, and audit processes
        ├── Align organizational policies with SOC 2 Trust Service Criteria
        └── Conduct internal and external audits to maintain SOC 2 certification.
		└──  Evidences	
```

### Checklist

* https://www.isms.online/app/uploads/2023/06/SOC2-Checklist.pdf
* https://www.mossadams.com/getmedia/a8baea51-3d03-4a84-a37c-a2e8d59df351/21-ADV-0751_SOC_2_Compliance_PRINTABLE_Checklist.pdf
* https://www.slideshare.net/slideshow/soc-2-type-2-checklist-part-1-v2finalpdf/263845098

### Policy Documentation Required
-   **Information Security Policy**
-   **Access Control Policy**
-   **Risk Management and Incident Response Policy**
-   **Change Management Policy**
-   **Encryption and Data Protection Policy**
-   **Audit Logging and Monitoring Policy**
-   **Business Continuity and Disaster Recovery Plan**
-   **Data Retention Policy**
-   **Vendor Management Policy**
-   **Penetration Testing Policy**

### Helpful Links
-   https://www.sans.org/security-resources/policies/general/pdf/information-security-policy
-   https://www.vanta.com/resources/soc-2-compliance-policy-templates
