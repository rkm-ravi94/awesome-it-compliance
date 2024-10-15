## COBIT (Control Objectives for Information and Related Technologies)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Application Development
│   │   └── Align development practices with COBIT’s control objectives for security and risk management
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
│   ├── Change Management
│   │   └── Follow COBIT’s guidelines for managing application changes with traceability
|		└──  Evidences
|		└──	 Tools
|			└── Email
|			└── JIRA Tickets
|
│   ├── Data Protection and Integrity
│   │   └── Implement controls to ensure the integrity and security of data processed by applications
|		└──  Evidences
|		└──  Tools
|			└──	Hashing of files ( application specific )
|			└── FIM ( file integrity monitoring )
|				└── Wazuh
|				└── TripWire
|				└── Aide
|				└── Samhain
|				└── Snoopy Logger
|			└── Encryption
|				└── KMS, CMEK, x509, GnuPG, PGP
|
│   └── Secure Coding Standards
│       └── Follow security standards and guidelines to ensure that applications meet compliance requirements
|		└──  Evidences
|		└── Tools 
|			└── SCA
|				└── SonarQube
|				└── GoSec ( golang )
|				└── Owasp Dependency Check
|				└── Snyk
│
├── IT Point of View (Operations and IT Management)
│   ├── IT Governance and Strategy
│   │   └── Align IT operations with COBIT’s governance framework for information management
|		└──  Evidences
|
│   ├── Risk Management and Compliance
│   │   └── Ensure IT risk management is in line with COBIT’s control objectives for reducing risk
|		└──  Evidences
|
│   ├── Change Management and Release Control
│   │   └── Implement change management processes to ensure controlled, compliant IT changes
|		└──  Evidences
|
│   ├── Incident Management and Response
│   │   └── Ensure that IT incidents are logged, tracked, and resolved in compliance with COBIT guidelines
|		└──  Evidences
|
│   └── Continuous Monitoring and Auditing
│       └── Regularly monitor IT systems and perform internal audits to ensure compliance
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Access Control and Identity Management
│   │   └── Ensure access control mechanisms comply with COBIT’s security control objectives.
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
│   ├── Network Security
│   │   └── Implement firewalls, IDS/IPS, and secure network configurations per COBIT guidelines
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
│   ├── Encryption and Data Security
│   │   └── Use encryption and security controls to protect sensitive information within systems
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Monitor network activities and ensure that logs are collected and retained for audits
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   └── Vulnerability Management
│       └── Conduct regular vulnerability assessments and apply security patches according to COBIT controls
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
├── COBIT Control Objectives
│   ├── Governance and Management of IT
│   │   └── Align IT strategy with enterprise goals using COBIT’s governance framework.
|		└──  Evidences
|
│   ├── Risk Management
│   │   └── Identify, assess, and mitigate IT risks in line with COBIT’s risk management practices.
|		└──  Evidences
|
│   ├── Information Security
│   │   └── Ensure that systems are secured using access controls, monitoring, and encryption.
|		└──  Evidences
|		└── Tools
|			└── All the tools discussed above.
|
│   ├── Compliance with Legal and Regulatory Requirements
│   │   └── Maintain compliance with industry standards and regulations using COBIT’s control frameworks
|		└──  Evidences
|
│   └── Performance Management
│       └── Use performance metrics to ensure IT systems meet organizational objectives and controls
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with COBIT’s guidelines on managing information and regulatory compliance
    │   └── Regularly review legal obligations and adapt systems and policies to meet COBIT’s objectives
	|		└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train staff on COBIT’s IT governance, security, and risk management principles
    │   └── Conduct regular training on managing changes, risks, and incidents within COBIT’s framework
	|		└──  Evidences
	|
    └── Management and Leadership
        ├── Align organizational strategy with COBIT’s governance and control objectives
        ├── Implement management oversight to ensure IT goals align with business objectives
        └── Ensure COBIT principles are integrated into enterprise IT governance and management processes
		└──  Evidences
```

### Checklist
* https://www.sdlcforms.com/PDFClientsDownload/COBIT_Checklist_and_Review.pdf
* https://www.scribd.com/document/413775656/Cobit-5-Checklist
* https://miroslawdabrowski.com/downloads/COBIT5/COBIT%205%20-%20Cheatsheet%20%5Bv1.0,%20Minimarisk%5D.pdf
* https://www.slideshare.net/slideshow/cobit5checklistpdf/252542498

### Policy Documentation Required

-   **IT Governance Framework**
-   **Risk Management Policy**
-   **Access Control and Identity Management Policy**
-   **Change Management Policy**
-   **Performance and Metrics Policy**
-   **Incident Response Plan**
-   **Data Protection and Encryption Policy**
-   **Audit and Monitoring Policy**
-   **Service Continuity and Recovery Plan**

### Helpful Links
-   https://www.isaca.org/resources/cobit
-   https://advisera.com/27001academy/knowledgebase/cobit-guide/
