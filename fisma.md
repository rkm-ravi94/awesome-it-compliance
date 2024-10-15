## FISMA (Federal Information Security Management Act)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Coding Practices
│   │   └── Follow secure development guidelines aligned with NIST SP 800-53 and FISMA requirements
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
│   ├── Encryption of Sensitive Data
│   │   └── Use FIPS 140-2 compliant encryption for protecting federal information
|		└──  Evidences
|		└── Tools
| 			└── mTLS ( mutual TLS ) for data in transit.
|			└── OpenSSL
|			└── LibreSSL
|			└── SSL/TLS at Loadbalancers, proxies for data in transit
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Application Logging and Auditing
│   │   └── Ensure that application-level access and activities are logged for FISMA compliance
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Vulnerability Management
│   │   └── Regularly scan applications for vulnerabilities and patch promptly
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Continuous Monitoring
│       └── Continuously monitor applications for security risks, ensuring adherence to FISMA standards
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── SuriCata
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Risk Assessment and Management
│   │   └── Perform regular risk assessments following the NIST Risk Management Framework (RMF)
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   ├── Access Control
│   │   └── Implement role-based access controls and multifactor authentication to restrict system access
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
│   ├── Incident Response
│   │   └── Establish a FISMA-compliant incident response plan based on NIST SP 800-61 guidelines
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Continuous Monitoring and Reporting
│   │   └── Implement ongoing monitoring for FISMA compliance, generating regular reports
|		└──  Evidences
|		└── Tools
|			└── OpenSCAP
|			└── Wazuh
|			└── Lynis
|			└── Scoutsuite
|			└── Prowler
|			└── Falco
|
│   ├── IT Security Policies
│   │   └── Enforce security policies that comply with FISMA and NIST standards for IT infrastructure
|		└──  Evidences
|
│   └── Data Backup and Recovery
│       └── Ensure secure, encrypted backups and regularly test disaster recovery procedures.
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
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Encryption and Data Protection
│   │   └── Use FIPS 140-2 validated encryption modules to secure federal data at rest and in transit.
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Network Security
│   │   ├── Use firewalls, IDS/IPS systems, and secure network segmentation to protect federal systems
│   │   └── Regularly audit and monitor network traffic for anomalies or unauthorized access
|		└──  Evidences
|		└──	 Tools
|			└── IDS/IPS
|				└── Snort + Snoby
|				└── SuriCata + Snoby
|				└── Wazuh
|				└── Zeek
|				└── SecurityOnion
|			└── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|
│   ├── Logging and Monitoring
│   │   └── Log access to federal systems and data, and regularly review logs for compliance
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
│   ├── Patch and Vulnerability Management
│   │   └── Regularly scan for vulnerabilities and apply security patches promptly
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Physical Security
│       └── Implement physical security controls to protect infrastructure handling federal data
|		└──  Evidences
|		└── Tools
|			└── Thales Luna HSM devices ( Physical Server Vault )
|			└── ZoneMinder/Motion (for video surveillance)
│			└── Security Onion/Nagios/MeshCentral ( for monitoring based on Sensors )
|
├── NIST and FISMA Frameworks
│   ├── NIST Risk Management Framework (RMF)
│   │   └── Follow the NIST RMF for managing security risks to federal information systems
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   ├── NIST SP 800-53 (Security and Privacy Controls)
│   │   └── Implement FISMA-compliant security controls as outlined in NIST SP 800-53
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   └── FISMA Annual Reporting
│       └── Provide regular compliance reports to the Office of Management and Budget (OMB)
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure all federal systems comply with FISMA’s security standards and NIST guidelines
    │   └── Maintain detailed documentation for FISMA audits and regulatory reviews
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train employees on FISMA requirements, including security awareness and incident handling
    │   └── Ensure that personnel with access to federal systems are security-cleared and trained
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Assign a security officer to oversee FISMA compliance and risk management
        ├── Align organizational security goals with FISMA and NIST frameworks
        └── Ensure that continuous improvement of security practices is a priority for the organization
		└──  Evidences
```

### Checklist

* https://www.uab.edu/it/home/images/files/FISMA-Researcher-Handbook_v102.pdf
* https://www.sailpoint.com/identity-library/fisma-compliance-checklist
* https://www.lepide.com/blog/fisma-compliance-checklist/
* https://sprinto.com/blog/fisma-compliance/


### Policy Documentation Required
-   **System Security Plan (SSP)**
-   **Risk Management Plan**
-   **Incident Response Plan**
-   **Access Control Policy**
-   **Security Awareness Training Policy**
-   **Continuous Monitoring Policy**
-   **Vulnerability Management Plan**
-   **Contingency Plan (Backup and Recovery)**
-   **Audit Control Policy**
-   **Physical Security Policy**

### Helpful Links
-   https://www.complianceforge.com/fisma-nist-800-53-compliance/
-   https://fedramp.org/documents/
