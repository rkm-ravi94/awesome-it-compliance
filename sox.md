## SOX (Sarbanes-Oxley Act)

```Tree
├── Developer's Point of View (Application Security)
│   ├── Secure Financial Application Development
│   │   └── Ensure secure development practices for financial systems.
|	|	└──  Evidences
|		└──  Tools
|			└── Aircloak (Data anonymization and privacy-preserving analytics)
|			└── ARX Data Anonymization Tool (Anonymization and pseudonymization of datasets)
|			└── FPE (Format-Preserving Encryption) by OpenSSL
|			└── DataMasker/Jailer (Masking of Data)
|			└── Mimesis
|			└── Faker/Python Faker Library (Generate fake data to replace personal information for testing)
|			└── Anonimatron (Database anonymization tool)
|	
│   ├── Data Integrity Controls
│   │   └── Ensure data integrity for financial records and reporting systems.
|	|	└──  Evidences
|   |		└── Tools ( File Integrity )
|	|			└── Wazuh
|	|			└── TripWire
|	|			└── Aide
|	|			└── Samhain
|	|			└── Snoopy Logger
|	
│   ├── Access Controls
│   │   └── Implement role-based access controls for financial data.
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
│   └── Audit Logging
│       └── Ensure that all access to financial data is logged and auditable.
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|	
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Authentication
│   │   └── Ensure strong authentication mechanisms (MFA) for accessing financial systems.
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
│   ├── IT General Controls (ITGCs)
│   │   ├── Change Management
│   │   ├── Access Controls
│   │   └── IT Operations (backup, disaster recovery)
|	|	└──  Evidences
|	
│   ├── Data Backup and Recovery
│   │   └── Ensure secure and timely backups for financial systems and data.
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
│   ├── Incident Response and Reporting
│   │   └── Create an incident response plan for security and financial reporting issues.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|	
│   ├── Change Management
│   │   └── Ensure that changes to financial systems are documented and auditable.
|	|	└──  Evidences
|		└──  Tools
|			└── JIRA/Trello/Email to track change requests
|			└── Confluence/Coda/GoogleDoc/Github etc to maintain changelogs
|	
│   └── Regular Auditing and Monitoring
│       └── Implement continuous monitoring for compliance and audit readiness.
|		└──  Evidences
|		└── Tools
|			└── Logging Tools
|			└── Application Monitoring Tools ( Newrelic )
|			└── Infra monitoring tools
|			└── Container Monitoring tools
|	
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Logging and Monitoring
│   │   └── Log all access and changes to financial data for audit purposes.
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|	
│   ├── Data Encryption
│   │   └── Encrypt sensitive financial data, both at rest and in transit.
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|	
│   ├── Secure Network Infrastructure
│   │   └── Implement firewalls, VPNs, and network segmentation for systems handling financial data
|	|	└──  Evidences
|		└──	 Tools
|			└── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|			└── VPN
|				└── OpenVPN
|				└── WireGuard
|				└── StrongSwan
|	
│   ├── Access Control
│   │   └── Restrict access to financial systems to authorized personnel only.
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
│   ├── System Availability
│   │   └── Ensure that financial systems have high availability and disaster recovery plans.
|	|	└──  Evidences
|	
│   └── Patch and Vulnerability Management
│       └── Regularly update and patch systems to ensure they remain secure
|		└──  Evidences
|	|	└── Tools
|	|		└── Vulnerability_Management_Tools
|	|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|	|			└── Image Vulnerability -> Trivy, Grype, Clair
|	|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|	|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|	|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|	|
|	|		└── Patch_Management_Tools
|	|			└── Cloud Native Patch Management System ( AWS, GCP, Azure )
|	|			└── Heimdall Patch Management ( 30 days free trial )
|	|			└── PDQ Deploy ( windows patch management )
|	|			└── Comodo
|	|			└── Miradore
|	|			└── SCM tools ( Chef, Puppet, Saltstack, Ansible )
|	
│
├── Internal Controls Over Financial Reporting (ICFR)
│   ├── Documentation of Controls
│   │   └── Document and maintain control over financial reporting processes.
|	|	└──  Evidences
|	
│   ├── Risk Assessment
│   │   └── Assess risks to financial reporting and establish mitigation strategies.
|	|	└──  Evidences
|	
│   └── Control Testing
│       └── Conduct regular testing of internal controls for financial reporting accuracy.
|		└──  Evidences
|	
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with Section 302 (Management Certification of Financial Statements)
    │   ├── Implement Section 404 (Assessment of Internal Controls) for financial reporting.
    │   └── Maintain accurate and auditable financial records
	|	└──  Evidences
	|	
    ├── HR and Employee Training
    │   ├── Train employees on SOX compliance requirements and ethical standards
    │   └── Enforce security and financial reporting policies across teams.
	|	└──  Evidences
	|	
    └── Management and Leadership
        ├── CEO and CFO certifications of financial reports
        ├── Ensure oversight of internal controls and audit processes
        └── Implement governance to ensure transparency and accuracy in financial reporting.
		└──  Evidences	
```

### Checklist

* https://go.plantemoran.com/rs/946-CTY-601/images/MC_RAAS_Internal%20Control%20Checklist_Interactive_Final.pdf
* https://www.sarbanes-oxley-101.com/sarbanes-oxley-checklist.htm
* https://community.dynamics.com/blogs/post/?postid=ad10360a-6390-48c4-9502-3823d0e8be1f
* https://www.cbh.com/wp-content/uploads/2024/08/SOX-Compliance-Checklist_Graphic_1481284677_PDF_092024.pdf

### Policy Documentation Required
-   **Internal Controls Over Financial Reporting (ICFR)**
-   **Access Control Policy**
-   **Change Management Policy**
-   **Audit Log Policy**
-   **Data Retention Policy**
-   **Backup and Recovery Policy**
-   **Incident Response Policy**
-   **Third-Party Vendor Management Policy**
-   **IT General Controls (ITGCs)**


### Helpful Links
-   https://templates.digitorysolutions.com/sox-policies-procedures-sample/
-   [https://www.soxtemplates.com/](https://www.soxtemplates.com/)
- https://safetyculture.com/checklists/sox-compliance/
