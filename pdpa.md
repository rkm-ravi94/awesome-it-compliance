## PDPA (Personal Data Protection Act - Singapore)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Privacy by Design
│   │   └── Embed privacy protection measures into the development process from the start (PDPA Section 24).
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
│   ├── Consent Management
│   │   └── Implement features for obtaining and managing consent for data collection (PDPA Section 13)
|	|	└──  Evidences
|	
│   ├── Data Minimization
│   │   └── Ensure only necessary personal data is collected for the purposes of processing (PDPA Section 18)
|	|	└──  Evidences
|	
│   ├── Data Access and Correction
│   │   └── Provide functionality for users to access and request corrections to their personal data (PDPA Section 21)
|	|	└──  Evidences
|	
│   └── Data Security and Encryption
│       └── Use encryption to protect personal data both in transit and at rest (PDPA Section 24)
|	|	└──  Evidences
|	
│
├── IT Point of View (Operations and IT Management)
│   ├── Data Access Controls
│   │   └── Implement role-based access controls and audit logs for access to personal data (PDPA Section 24)
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
│   ├── Data Retention and Disposal
│   │   └── Ensure personal data is retained only as long as necessary and disposed of securely (PDPA Section 25)
|	|	└──  Evidences
|	
│   ├── Data Breach Notification
│   │   └── Notify the Personal Data Protection Commission (PDPC) and affected individuals in case of a data breach (PDPA Section 26D)
|	|	└──  Evidences
|	
│   ├── Consent Withdrawal Management
│   │   └── Implement processes to allow individuals to withdraw consent for processing their data (PDPA Section 16)
|	|	└──  Evidences
|	
│   └── Monitoring and Incident Response
│       └── Establish systems to monitor for unauthorized access and respond to security incidents involving personal data.
|	|	└──  Evidences
|	
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Data Encryption
│   │   └── Encrypt personal data to protect it during transmission and storage (PDPA Section 24).
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|	
│   ├── Logging and Monitoring
│   │   └── Implement logging and monitoring to track access to systems handling personal data (PDPA Section 24).
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|	
│   ├── Network Security and Segmentation
│   │   └── Ensure secure network configurations and segment systems processing personal data.
|	|	└──  Evidences
| 		└── Tools
|			└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|			└── Safeline
|			└── ModSecurity
|			└── Shadow Daemon 
|	
│   ├── Access Controls
│   │   └── Enforce strict access control policies to limit access to personal data only to authorized personnel.
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
│   └── Vulnerability and Patch Management
│       └── Regularly scan for vulnerabilities and apply security patches to reduce risks.
|	|	└──  Evidences
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
├── Data Subject Rights (PDPA Sections 21, 22, 24)
│   ├── Right to Access
│   │   └── Ensure individuals can request access to their personal data held by an organization.
|	|	└──  Evidences
|	
│   ├── Right to Correction
│   │   └── Allow individuals to request corrections to any inaccurate or incomplete personal data.
|	|	└──  Evidences
|	
│   ├── Right to Withdraw Consent
│   │   └── Implement mechanisms to allow individuals to withdraw consent for data processing.
|	|	└──  Evidences
|	
│   └── Data Portability (Future Development)
│       └── Plan for future data portability regulations in Singapore to allow for easier transfer of data between service providers.
|	|	└──  Evidences
|	
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with PDPA when entering contracts with third-party service providers handling personal data
    │   └── Maintain records of data processing activities and ensure regular audits for compliance with the PDPA.
    |	└──  Evidences
	|	
    ├── HR and Employee Training
    │   ├── Train employees on PDPA requirements and secure data handling practices
    │   └── Provide regular training on data protection, consent management, and breach response.
	|	└──  Evidences
	|	
    └── Management and Leadership
        ├── Appoint a Data Protection Officer (DPO) to oversee PDPA compliance
        ├── Ensure regular reviews and audits of data protection policies and procedures
        └── Align data protection strategies with PDPA requirements and future amendments to the act.
		└──  Evidences
```

### Checklist

* https://www.scribd.com/document/357041516/Pdpa
* https://www.faithacts.org.sg/images/aboutus/pdpa/pdpa_sop.pdf
* https://www.ummc.edu.my/files/ethic/MCHRS/6%20Privacy%20Data%20Protection/Compliance%20to%20Personal%20Data%20Protection%20Act%20(PDPA)%20a%20quick%20guide.pdf



### Policy Documentation Required
-   **Data Protection Policy**
-   **Consent Management Policy**
-   **Data Retention and Deletion Policy**
-   **Access Control and Data Minimization Policy**
-   **Data Subject Rights Policy (Access, Correction, Portability)**
-   **Incident Response and Breach Notification Policy**
-   **Third-Party Vendor Policy**
-   **Privacy Policy**

### Helpful Links
-   https://www.pdpc.gov.sg/Help-and-Resources/2020-PDPA-Handbook
-   https://www.termly.io/resources/templates/pdpa-compliant-privacy-policy/
