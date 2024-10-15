## GLBA (Gramm-Leach-Bliley Act)
```tree structure
├── Developer's Point of View (Application Security)
│   ├── Secure Application Development
│   │   └── Ensure that applications handling financial data comply with GLBA security requirements
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
│   ├── Encryption and Data Protection
│   │   └── Encrypt sensitive financial data both in transit and at rest (GLBA Safeguards Rule)
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Secure Access to Customer Data
│   │   └── Implement access controls to ensure only authorized users can access customer financial data
|		└──  Evidences
|		└── Tools
|			└── MFA
|			└── KeyCloak
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Data Integrity and Confidentiality
│   │   └── Ensure application features protect the integrity and confidentiality of financial information
|		└──  Evidences
|		└── Tools ( File Integrity )
|			└── Wazuh
|			└── TripWire
|			└── Aide
|			└── Samhain
|			└── Snoopy Logger
|
│   └── Logging and Auditing
│       └── Implement logging mechanisms to track access and changes to financial data for audit purposes
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control and Identity Management
│   │   └── Ensure that access to systems processing financial data is restricted to authorized personnel
|		└──  Evidences
|		└── Tools
|			└── MFA
|			└── KeyCloak
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Incident Response and Breach Notification
│   │   └── Establish incident response plans to address breaches of financial data and notify affected individuals (GLBA Safeguards Rule)
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Data Encryption and Security
│   │   └── Use encryption to secure customer data during storage and transmission
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Continuous Monitoring and Vulnerability Management
│   │   └── Regularly monitor systems for vulnerabilities and suspicious activities, applying patches promptly
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Data Retention and Disposal Policies
│       └── Establish policies for secure retention and disposal of financial records when no longer needed
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Encryption and Data Protection
│   │   └── Ensure that sensitive financial data is encrypted both at rest and in transit to prevent unauthorized access
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Network Security
│   │   └── Implement firewalls, secure network segmentation, and IDS/IPS to protect financial systems from unauthorized access
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
│   │   └── Log all access to systems processing financial data and regularly review logs for anomalies
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Access Control
│   │   └── Enforce strict access control policies to ensure only authorized personnel can access sensitive financial data
|		└──  Evidences
|		└── Tools
|			└── MFA
|			└── KeyCloak
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   └── Patch and Vulnerability Management
│       └── Regularly assess and patch vulnerabilities in systems that store or process financial data
|		└──  Evidences
|		└── Tools
|			└── Vulnerability_Management_Tools
|				└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|				└── Image Vulnerability -> Trivy, Grype, Clair
|				└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|				└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|				└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
|			└── Patch_Management_Tools
|				└── Cloud Native Patch Management System ( AWS, GCP, Azure )
|				└── Heimdall Patch Management ( 30 days free trial )
|				└── PDQ Deploy ( windows patch management )
|				└── Comodo
|				└── Miradore
|				└── SCM tools ( Chef, Puppet, Saltstack, Ansible )
|
│
├── GLBA Safeguards Rule
│   ├── Risk Assessment
│   │   └── Conduct risk assessments to identify potential security risks to customer financial data
|		└──  Evidences
|		└── Tools
|			└── Vulnerability_Management_Tools
|				└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|				└── Image Vulnerability -> Trivy, Grype, Clair
|				└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|				└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|				└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├── Information Security Program
│   │   └── Develop and implement a comprehensive information security program to protect customer data
|		└──  Evidences
|		└──  Tools
|			└── OpenDLP
|			└── MyDLP
|			└── Wazuh
|			└── Tinfoil Security
|			└── ModSecurity
|
│   ├── Employee Training
│   │   └── Train employees on secure handling of customer data and GLBA compliance requirements
|		└──  Evidences
|
│   └── Service Provider Oversight
│       └── Ensure third-party service providers handling customer data are compliant with GLBA’s Safeguards Rule
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure that financial institutions comply with GLBA’s privacy and security requirements
    │   └── Maintain compliance documentation for audits and regulatory reviews
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Provide regular training for employees on GLBA’s privacy and security requirements, as well as secure data handling practices
    │   └── Conduct training sessions on incident response protocols for breaches of financial data
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Assign leadership to oversee GLBA compliance and the security of financial data
        ├── Regularly review and audit information security policies and practices to ensure they meet GLBA standards
        └── Ensure that third-party vendors handling financial data comply with GLBA’s requirements
		└──  Evidences

```

### Checklist

* https://studentprivacycompass.org/wp-content/uploads/2023/07/FPF-GLBA-Checklist.docx-2.pdf
* https://www.spirion.com/blog/glba-compliance-checklist-financial-services
* https://preyproject.com/blog/glba-compliance-checklist-an-in-depth-view-of-the-safeguards-rule


### Policy Documentation Required
-   **Information Security Policy**
-   **Customer Data Protection Policy**
-   **Risk Management and Incident Response Policy**
-   **Access Control Policy**
-   **Encryption and Data Protection Policy**
-   **Third-Party Service Provider Policy**
-   **Audit and Monitoring Policy**
-   **Employee Training Policy**
-   **Business Continuity and Recovery Plan**

### Helpful Links
-   https://advisera.com/27001academy/documentation-toolkit-for-banks/
-   https://www.exigobusiness.com/glba-compliance-checklist/
