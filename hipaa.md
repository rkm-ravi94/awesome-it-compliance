## HIPAA

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Privacy and Security of Protected Health Information (PHI)
│   │   └── Ensure that PHI is protected in applications through encryption and access controls
|		└──  Evidences
|		└──  Tools
|			└──  Encryption
|				└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|				└── Libgcrypt ( for customer managed encryption )
|				└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|				└── GnuTLS ( mTLS based comms )
|				└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
|			└──  Access Controls
|				└── MFA ( Google Auth )
|				└── KeyCloak
|				└── OpenIAM
|				└── OpenLDAP 
|				└── FreeIPA
|				└── Apache syncope
|				└── IAM ( Cloud Native )
|				└── RBAC ( role based access controls ) application native
|
│   ├── Secure Authentication and Authorization
│   │   └── Implement strong authentication methods (e.g., MFA) for users accessing PHI
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
│   ├── Audit Trails and Logging
│   │   └── Ensure applications track access and modifications to PHI for audit purposes
|		└──  Evidences
|		└──	 Tools
|			└── Elasticsearch, Logstash, Kibana (ELK Stack)
|			└──	Graylog
|			└── Loki
|			└──	RSYSLOG
|			└──	OpenSearch (Open-source fork of Elasticsearch)
|			└──	Newrelic One
|			└──	Wazuh
|
│   ├── Data Encryption
│   │   └── Use encryption mechanisms to secure PHI during transmission and storage
|		└──  Evidences
|		└── Tools
| 			└── mTLS ( mutual TLS ) for data in transit.
|			└── SSL/TLS at Loadbalancers, proxies for data in transit
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   └── Access Controls
│       └── Enforce role-based access controls to ensure only authorized users access PHI
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
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Authentication
│   │   └── Limit access to PHI to authorized personnel and systems
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
│   ├── Risk Assessment
│   │   └── Conduct regular risk assessments to identify and mitigate vulnerabilities
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├── Backup and Disaster Recovery
│   │   └── Ensure secure, encrypted backups of PHI and have a disaster recovery plan in place
|		└──  Evidences
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
│   ├── Data Breach Response
│   │   └── Establish procedures for reporting breaches and notifying affected individuals within 60 days
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Regular Training and Awareness
│   │   └── Train staff on HIPAA compliance, data protection, and breach reporting
|		└──  Evidences
|
│   └── IT Security Policies
│       └── Implement security policies and procedures that comply with the HIPAA Security Rule
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Data Encryption
│   │   └── Encrypt PHI during transmission (TLS/SSL) and at rest (AES-256)
|		└──  Evidences
|		└── Tools
| 			└── mTLS ( mutual TLS ) for data in transit.
|			└── SSL/TLS at Loadbalancers, proxies for data in transit
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Log access and changes to PHI and review logs regularly
|		└──  Evidences
|		└──	 Tools
|			└── Elasticsearch, Logstash, Kibana (ELK Stack)
|			└──	Graylog
|			└── Loki
|			└──	RSYSLOG
|			└──	OpenSearch (Open-source fork of Elasticsearch)
|			└──	Newrelic One
|			└──	Wazuh
|
│   ├── Network Segmentation
│   │   └── Separate PHI systems from other internal networks to ensure data isolation
|		└──  Evidences
|		└──	 Tools
|			└── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|
│   ├── Intrusion Detection and Prevention (IDS/IPS)
│   │   └── Use IDS/IPS to detect and prevent unauthorized access to PHI systems
|		└──  Evidences
|		└──	 Tools
|			└── IDS/IPS
|				└── Snort + Snoby
|				└── SuriCata + Snoby
|				└── Wazuh
|				└── Zeek
|				└── SecurityOnion
|
│   └── Physical Security
│       └── Implement physical security controls to protect servers and systems storing PHI
|		└──  Evidences
|		└── Tools
|			└── Thales Luna HSM devices ( Physical Server Vault )
|			└── ZoneMinder/Motion (for video surveillance)
│			└── Security Onion/Nagios/MeshCentral ( for monitoring based on Sensors )
|
│
├── HIPAA Security Rule Compliance (Administrative, Physical, and Technical Safeguards)
│   ├── Administrative Safeguards
│   │   ├── Conduct risk assessments and document policies
│   │   └── Designate a security officer responsible for compliance
|		└──  Evidences
|
│   ├── Physical Safeguards
│   │   ├── Secure facilities where PHI is stored (e.g., access controls, alarms)
│   │   └── Implement controls for workstation and device security
|		└──  Evidences
|
│   └── Technical Safeguards
│       ├── Implement access controls for PHI (e.g., passwords, role-based access)
│       └── Implement mechanisms for auditing and tracking access to PHI
|		└──  Evidences
|
│
├── Breach Notification Rule
│   ├── Breach Reporting Procedures
│   │   └── Establish procedures for notifying individuals and the U.S. Department 
of Health and Human Services (HHS)
|	|	└──  Evidences
|	|
│   ├── Timely Breach Notification
│   │   └── Ensure breaches are reported within 60 days
|	|	└──  Evidences
|
│   └── Breach Impact Assessment
│       └── Assess and document the scope and severity of breaches involving PHI
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure all business associates (vendors) sign Business Associate Agreements (BAAs)
    │   ├── Comply with both the Privacy Rule and the Security Rule for PHI protection
    │   └── Implement policies to address HIPAA compliance across the organization
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Provide HIPAA-specific training to all employees handling PHI
    │   └── Train staff on data breach identification and response procedures
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Appoint a HIPAA compliance officer
        ├── Develop an information security program that aligns with HIPAA requirements
        └── Regularly review and update HIPAA policies and procedures
		└──  Evidences
```

### Checklist

* https://www.prms.com/media/2160/hipaa-compliance-checklist.pdf
* https://www.psychiatry.org/File%20Library/Psychiatrists/Practice/Practice-Management/HIPAA/HIPAA-Compliance-Checklist.pdf
* https://www.healthit.gov/sites/default/files/comments_upload/hipaa-security-checklist.pdf
* https://www.nextdlp.com/hubfs/hipaa-complaince-checklist.pdf


### Policy Documentation Required
-   **Privacy and Security Policies**
-   **Access Control and Identity Management Policy**
-   **Incident Response and Breach Notification Policy**
-   **Data Encryption and Transmission Policy**
-   **Workforce Training and Awareness Policy**
-   **Audit Control and Monitoring Policy**
-   **Contingency Plan (Backup and Disaster Recovery)**
-   **Sanction Policy**
-   **Business Associate Agreements**
-   **Physical Safeguards Policy**

### Helpful Links
-   [https://www.hipaapoliciesandprocedures.com/](https://www.hipaapoliciesandprocedures.com/)
-   https://www.hipaajournal.com/free-hipaa-compliance-checklist-download/
