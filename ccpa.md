## CCPA (California Consumer Privacy Act)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Data Minimization
│   │   └── Collect only necessary personal information from users 
|		└──  Evidences
|				└── Screenshots of UI for data scope ( profile, email, gallery |permission etc )
|				└── Sceenshots, Links to codeblock for above evidence.
|				└── Live Demo of Application is also asked by Auditor.
|
│   ├── User Consent Management
│   │   └── Implement mechanisms for users to opt-out of data collection (e.g., |“Do Not Sell My Info”)
|		└──  Evidences
|				└── Screenshots of UI for data scope ( profile, email, gallery |permission etc ) with the consent window ( webview for App )
|				└── Screenshot, Links to codeblock to assert above logic.
|				└── Live Demo of Application is also asked by Auditor.
|
│   ├── Data Deletion Features
│   │   └── Provide users with the ability to delete their personal information upon request
|		└── Evidences
|			└── Screenshot, Links to codeblock to assert above logic.
|			└── Data Deletion consent, Terms & Conditions for end user on UI.
|			└── Live Demo of Application is also asked by Auditor.
|
│   ├── Data Portability
│   │   └── Implement functionality to export personal data in a structured format 
upon request
|		└── Evidences

│   └── User Interface for Privacy Controls
│       └── Ensure privacy settings (opt-out, data access, etc.) are easily accessible in the UI
|		└── Evidences

│
├── IT Point of View (Operations and IT Management)
│   ├── Data Access and Deletion Requests
│   │   └── Implement processes to handle user requests for data access and deletion
|		└── Evidences
|
│   ├── Data Inventory and Mapping
│   │   └── Maintain a detailed inventory of personal data collected, stored, and shared
|		└── Evidences
|
│   ├── Incident Response and Breach Notification
│   │   └── Establish a process for notifying consumers in case of a data breach
|		└── Evidences
|
│   ├── Vendor Management
│   │   └── Ensure third-party vendors comply with CCPA privacy regulations
|	|	|	└── Ensure to collect CCPA Documentation from vendors or involve them in the audit.
|		└── Evidences
|
│   └── Data Retention Policies
|	|	└── Ensure to have a Data Retention Policy ( this would be required pre hand to be submitted before audit ).
│       └── Define retention periods for personal data and ensure timely deletion as per CCPA requirements.
|	|	|	└── Collect screenshots, logs, stdout files from a periodic deletion as evidence.
|		└── Evidences
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Data Encryption
│   │   └── Encrypt personal data at rest and in transit to protect it from unauthorized access.
|		└── Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Log access to personal data and monitor for unauthorized access or modifications
|		└── Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
│
│   ├── Data Segmentation
│   │   └── Segment systems containing personal data from other networks for additional security
|		└── Evidences
|		└── Tools
|			└── Jitsu
|			└── Apache unomi
│
│   ├── Access Controls
│   │   └── Implement strong access controls to limit who can view and process personal information
|		└── Evidences
|		└── Tools
|			└── MFA ( Google Auth )
|			└── KeyCloak
|			└── OpenIAM
|			└── OpenLDAP 
|			└── FreeIPA
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
│
│   └── Vulnerability Management
│       └── Regularly scan and patch systems that process personal information
|		└── Evidences
|		└── Tools
|			└── Cloud Native Patch Management System ( AWS, GCP, Azure )
|			└── Heimdall Patch Management ( 30 days free trial )
|			└── PDQ Deploy ( windows patch management )
|			└── Comodo
|			└── Miradore
|			└── SCM tools ( Chef, Puppet, Saltstack, Ansible )
│
├── Consumer Rights Management
│   ├── Right to Access
│   │   └── Allow consumers to request and obtain the personal information collected about them
|		└── Evidences
│
│   ├── Right to Delete
│   │   └── Provide consumers with the ability to request deletion of their personal data
|		└── Evidences
│
│   ├── Right to Opt-Out of Sale of Personal Information
│   │   └── Provide a mechanism for consumers to opt-out of the sale of their personal information
|		└── Evidences
│
│   └── Right to Non-Discrimination
│       └── Ensure that consumers who exercise their CCPA rights are not discriminated against
|		└── Evidences
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure all privacy notices are updated to reflect data collection practices
    │   ├── Maintain records of consent and opt-out requests
    │   └── Comply with the CCPA requirements for processing and sharing personal data
	|	└── Evidences

    ├── HR and Employee Training
    │   ├── Train employees on CCPA rights and compliance requirements
    │   └── Provide training on handling consumer data requests (access, deletion, opt-out)
    |	└── Evidences
	│
    └── Management and Leadership
    |   ├── Assign a Data Privacy Officer (DPO) or equivalent to oversee CCPA compliance
    |   └── Conduct regular assessments of privacy practices to ensure ongoing compliance
	|	└── Evidences
```

### Checklist
* https://www.securitycompass.com/wp-content/uploads/Security-Compass-CCPA-Compliance-Checklist.pdf
* https://www.memcyco.com/home/ccpa-compliance-checklist/
*  https://www.cookielaw.org/resources/ccpa-policy-template/
*  https://www.termly.io/resources/templates/ccpa-privacy-policy-template/

### Policy Documentation Required

-   **Privacy Policy**
-   **Data Subject Rights Policy (Access, Deletion, Opt-Out)**
-   **Data Retention and Deletion Policy**
-   **Consent Management Policy**
-   **Incident Response and Breach Notification Policy**
-   **Third-Party Service Provider Agreement**
-   **Do Not Sell My Information Policy**
-   **Data Protection Policy**
-   **User Consent Withdrawal Policy**


### Helpful Links

* https://oag.ca.gov/privacy/ccpa
* https://www.delphix.com/glossary/what-is-ccpa-compliance
* https://www.onetrust.com/blog/ultimate-guide-to-ccpa-compliance/
