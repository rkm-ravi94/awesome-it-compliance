## FedRAMP

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Software Development Lifecycle (SDLC)
│   │   └── Implement secure coding practices in accordance with FedRAMP security controls.
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
│   ├── Data Encryption in Applications
│   │   └── Ensure that sensitive data is encrypted both in transit (TLS/SSL) and at rest (AES-256)
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Application Logging and Auditing
│   │   └── Ensure applications log access to sensitive data and retain logs for auditing purposes.
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Role-Based Access Control (RBAC)
│   │   └── Implement fine-grained access control for applications processing federal data
|		└──  Evidences
|		└── Tools
|			└── KeyCloak/Okta
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native.
|
│   └── Continuous Monitoring
│       └── Regularly test applications for vulnerabilities and compliance with FedRAMP standards
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Identity Management
│   │   └── Ensure access to systems processing federal data is tightly controlled and monitored.
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
│   ├── Incident Response and Reporting
│   │   └── Establish a FedRAMP-compliant incident response plan for reporting breaches to federal agencies.
|		└──  Evidences
|
│   ├── Continuous Monitoring
│   │   └── Implement ongoing vulnerability assessments and system health checks
|		└──  Evidences
|
│   ├── Security Operations Center (SOC) Integration
│   │   └── Ensure that the SOC monitors and responds to security incidents 24/7
|		└──  Evidences
|		└── Tools
|			└── Pagerduty
|			└── SOCRadar
|
│   └── Configuration Management
│       └── Maintain strict controls for system configurations, ensuring compliance with FedRAMP baselines
|		└──  Evidences
|		└── Tools 
|			└── SCM tools
|				└── Chef, Puppet, Saltstack, Ansible
|				└── OpenSCAP, Packer
|				└── Terraform ( userdata )
|				└── Golden Images ( Self Baked AMIs with approved applications )
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Network Security
│   │   └── Implement secure network architectures, including firewalls and VPNs, to protect federal data.
|		└──  Evidences
| 		└── Tools
|			└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|			└── Safeline
|			└── ModSecurity
|			└── Shadow Daemon 
|			└── VPN -> OpenVPN, WireGuard, StrongSwan etc
|
│   ├── Encryption and Key Management
│   │   └── Use FIPS 140-2 validated encryption algorithms and manage encryption keys securely
|		└──  Evidences
|		└── Algorithms
|			└── SHA-256, SHA-384, SHA-512
|			└── KMS ( AWS, GCP, Azure )
|			└── Hashicorp Vault
|
│   ├── Logging and Monitoring
│   │   └── Ensure that access to infrastructure is logged, and logs are reviewed for anomalies
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Secure Cloud Infrastructure
│   │   └── Ensure cloud environments meet FedRAMP Moderate or High security baselines
|		└──  Evidences
|		└── Tools
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Vulnerability Management
│       └── Regularly scan infrastructure for vulnerabilities and patch promptly
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|
│
├── Authorization Process
│   ├── FedRAMP Authorization Packages
│   │   └── Prepare and submit security documentation for authorization (SSP, SAR, POA&M)
|		└──  Evidences
|
│   ├── Third-Party Assessment Organizations (3PAO)
│   │   └── Work with a FedRAMP-approved 3PAO to assess the security of the system
|		└──  Evidences
|
│   └── Ongoing Assessment and Authorization (Continuous ATO)
│       └── Maintain authorization by continuously monitoring security controls and providing updates
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure that all systems processing federal data comply with FedRAMP regulations
    │   └── Maintain contracts and service-level agreements that reflect FedRAMP security requirements
	|		└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train personnel on FedRAMP security controls, policies, and procedures
    │   └── Conduct regular security awareness training specific to federal data handling
	|		└──  Evidences
	|
    └── Management and Leadership
        ├── Assign a security officer responsible for FedRAMP compliance
        ├── Align organizational goals with FedRAMP security and authorization objectives
        └── Conduct regular reviews of security practices to maintain FedRAMP authorization
		└──  Evidences
```

### Checklist

*  https://reciprocity.com/resources/checklist-for-fedramp-requirements/
*  https://www.databank.com/wp-content/uploads/2018/08/DataBank-FedRAMP-Checklist.pdf
*  https://www.fedramp.gov/assets/resources/documents/FedRAMP_Security_Controls_Baseline.xlsx

### Policy Documentation Required

 -   **System Security Plan (SSP)**
-   **Access Control Policy**
-   **Incident Response Plan**
-   **Continuous Monitoring Plan**
-   **Configuration Management Policy**
-   **Data Encryption and Protection Policy**
-   **Contingency Plan (Backup and Disaster Recovery)**
-   **Audit Log Policy**
-   **Penetration Testing Policy**
-   **Personnel Security Policy**

### Helpful Links
-   https://www.fedramp.gov/templates/
-   https://www.fedramp.gov/documents/
