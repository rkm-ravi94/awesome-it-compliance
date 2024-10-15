## GDPR

``` Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Data Privacy by Design
│   │   └── Implement privacy features during development (e.g., anonymization, pseudonymization)
|		└──  Evidences
|		└──  Tools
|			└── Aircloak (Data anonymization and privacy-preserving analytics)
|			└── ARX Data Anonymization Tool (Anonymization and pseudonymization of datasets)
|			└── FPE (Format-Preserving Encryption) by OpenSSL
|			└── DataMasker/Jailer (Masking of Data)
|			└── Mimesis
|			└── Faker/Python Faker Library (Generate fake data to replace personal information for testing)
|			└── Anonimatron (Database anonymization tool)
|
│   ├── Data Minimization
│   │   └── Only collect and process necessary personal data
|		└──  Evidences
|
│   ├── User Consent Management
│   │   └── Implement user consent mechanisms (e.g., cookie banners, opt-ins)
|		└──  Evidences
|
│   ├── Right to Data Portability
│   │   └── Provide users the ability to download their personal data in a structured format
|		└──  Evidences
|
│   └── Right to be Forgotten (Data Erasure)
│       └── Provide mechanisms for users to request data deletion
|		└──  Evidences
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Access Control
│   │   └── Ensure proper access management and logging of access to personal data
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
│   ├── Data Breach Response
│   │   ├── Establish procedures for reporting breaches within 72 hours
│   │   └── Incident response plans for data breaches
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Data Retention Policies
│   │   └── Implement policies to regularly review and delete outdated personal data
|		└──  Evidences
|
│   └── Data Subject Rights Fulfillment
│       └── Ensure data subjects can exercise their rights (access, correction, deletion)
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Encryption
│   │   └── Encrypt personal data at rest and in transit
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Monitor and log access to personal data
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
│   ├── Secure Data Transfers
│   │   └── Ensure data transfers between EU and non-EU countries are lawful (e.g., Standard Contractual Clauses)
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|
│   ├── Vulnerability Management
│   │   └── Regularly scan and patch systems handling personal data
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Data Storage Segmentation
│       └── Separate environments where personal data is processed and stored
|		└──  Evidences
|		└── Tools
|			└── Jitsu
|			└── Apache unomi
│
├── Data Protection Officer (DPO) Responsibilities
│   ├── Appoint a DPO if required
│   ├── Monitor compliance with GDPR
│   ├── Serve as a point of contact for regulators and individuals
│   └── Conduct regular audits of data protection processes
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure lawful basis for processing personal data (e.g., consent, contract)
    │   ├── Maintain records of data processing activities
    │   └── Regularly review data protection policies
	|	└──  Evidences
	|
    ├── HR/Marketing
    │   ├── Ensure marketing practices comply with consent requirements
    │   ├── Train employees on GDPR and data handling practices
    │   └── Review recruitment and employee data processing practices
	|	└──  Evidences
	|
    └── Data Subject Rights
        ├── Right to Access (SARs - Subject Access Requests)
        ├── Right to Rectification (Correct inaccurate data)
        ├── Right to Restrict Processing
        └── Right to Object to Automated Decision-Making (e.g., profiling)
		└──  Evidences

```

### Checklist

* https://www.vistainfosec.com/wp-content/uploads/2021/02/GDPR-Compliance-Checklist-2022_compressed.pdf
* https://www.controlcase.com/gdpr-starter-guide-checklist
* https://www.lw.com/admin/Upload/Documents/LW-Privacy-GDPR-Compliance-Checklist.pdf


### Policy Documentation Required
-   **Data Protection Policy**
-   **Data Retention and Deletion Policy**
-   **Data Breach Notification Policy**
-   **Consent Management Policy**
-   **Privacy Policy**
-   **Access Control and Security Policy**
-   **Data Subject Rights Policy**
-   **Third-Party Vendor Management Policy**
-   **Data Minimization Policy**
-   **Data Portability Policy**
-   **Impact Assessment Policy (DPIA)**

### Helpful Links
-   https://gdpr.eu/document-templates/
-   https://www.itgovernance.eu/en-ie/gdpr-templates
