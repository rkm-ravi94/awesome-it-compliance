## FERPA (Family Educational Rights and Privacy Act)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Privacy by Design
│   │   └── Ensure that privacy principles are embedded into the development of applications handling student records
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
│   ├── Consent Management
│   │   └── Implement functionality to obtain and manage parental or student consent for data sharing (FERPA requirement)
|		└──  Evidences
|
│   ├── Data Access and Correction
│   │   └── Provide features that allow students or parents to access and request corrections to education records
|		└──  Evidences
|
│   ├── Data Security and Encryption
│   │   └── Encrypt student data both in transit and at rest to protect it from unauthorized access
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   └── Logging and Auditing
│       └── Implement logging of access to student records to ensure compliance with FERPA’s privacy requirements
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
│   ├── Access Controls and Identity Management
│   │   └── Implement strong access control mechanisms to restrict access to student education records (FERPA Section 99.31)
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
│   ├── Data Breach Notification
│   │   └── Establish procedures to notify students, parents, and authorities in case of unauthorized access or data breaches.
|		└──  Evidences
|
│   ├── Data Retention and Disposal
│   │   └── Ensure that student records are retained as per the institutional policy and securely deleted when no longer required
|		└──  Evidences
|
│   ├── Incident Response and Monitoring
│   │   └── Monitor IT systems for unauthorized access to education records and respond to incidents promptly
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|
│   └── Data Consent and Sharing Management
│       └── Ensure systems provide the ability to manage and track consent for sharing education records with third parties
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Data Encryption
│   │   └── Ensure student data is encrypted both in transit and at rest to protect against unauthorized access
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Log all access to systems handling student records and monitor for anomalies
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Access Controls
│   │   └── Enforce strict access control mechanisms to limit access to education records to authorized personnel
|		└──  Evidences
|		└── Tools
|			└── MFA
|			└── KeyCloak
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Network Security and Segmentation
│   │   └── Implement secure network configurations and segment systems processing education records from other networks
|		└──  Evidences
| 		└── Tools
|			└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|			└── Safeline
|			└── ModSecurity
|			└── Shadow Daemon 
|
│   └── Vulnerability and Patch Management
│       └── Regularly scan for vulnerabilities and apply patches to systems that store or process education records
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
├── Data Subject Rights (FERPA Regulations)
│   ├── Right to Access
│   │   └── Allow students or parents to request access to their education records (FERPA Section 99.10)
|		└──  Evidences
|
│   ├── Right to Request Correction
│   │   └── Allow parents or students to request corrections to inaccurate or misleading education records (FERPA Section 99.20)
|		└──  Evidences
|
│   └── Right to Control Disclosure
│       └── Ensure that students or parents can control the disclosure of education records, except under specific circumstances (FERPA Section 99.30)
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with FERPA’s privacy and security requirements for handling student education records
    │   └── Maintain documentation and records for audits and regulatory compliance reviews by the Department of Education
	|		└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train employees on FERPA requirements, including secure handling and protection of student records
    │   └── Provide regular training on privacy policies, consent management, and incident response
	|		└──  Evidences
	|
    └── Management and Leadership
        ├── Assign leadership to oversee FERPA compliance efforts and data protection strategies
        ├── Ensure regular audits of institutional practices to maintain FERPA compliance
        └── Align organizational data management policies with FERPA’s privacy and security standards
		└──  Evidences
```

### Checklist

* https://www.intradyn.com/ferpa-compliance-checklist/
* https://store.eset.com/us/assets/usweb/files/landing-pages/pdf/FERPAChecklist.pdf?srsltid=AfmBOorhBxlABYQXDUpyzeK_B_fq85cpRP0d31yd7O949j4EmlLJvprA
* https://nacada.ksu.edu/Portals/0/Resources/documents/privacy_checklist.pdf
* https://d0.awsstatic.com/whitepapers/compliance/AWS_FERPA_Whitepaper.pdf

### Policy Documentation Required
-   **Privacy and Security Policy for Student Records**
-   **Access Control Policy**
-   **Data Breach Notification Policy**
-   **Data Access and Correction Policy**
-   **Data Retention and Deletion Policy**
-   **Logging and Monitoring Policy**
-   **Incident Response Plan**
-   **Parental Consent Policy for Data Sharing**
-   **Third-Party Data Sharing Policy**


### Helpful Links
-   https://studentprivacy.ed.gov/ferpa-model-notification-rights-under-ferpa-elementary-secondary-schools
-   https://studentprivacy.ed.gov/
