## CISA (Cybersecurity Information Sharing Act)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Data Sharing Mechanisms
│   │   └── Implement secure APIs or interfaces for sharing cybersecurity data with CISA
|		└──  Evidences
|
│   ├── Anonymization of Shared Data
│   │   └── Ensure that any shared data is anonymized to protect user privacy
|		└──  Evidences
|
│   ├── Secure Data Transmission
│   │   └── Use secure communication protocols (TLS/SSL) when transmitting cybersecurity information
|		└──  Evidences
|		└── Tools
| 			└── mTLS ( mutual TLS ) for data in transit.
|			└── SSL/TLS at Loadbalancers, proxies for data in transit
|
│   ├── Application Logging
│   │   └── Ensure logs related to cybersecurity incidents are retained and available for sharing
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   └── Data Integrity Controls
│       └── Ensure data shared with CISA has not been tampered with
|		└──  Evidences
|		└── Tools ( File Integrity )
|			└── Wazuh
|			└── TripWire
|			└── Aide
|			└── Samhain
|			└── Snoopy Logger
│
├── IT Point of View (Operations and IT Management)
│   ├── Incident Reporting Procedures
│   │   └── Establish clear processes for reporting cybersecurity incidents to CISA
|		└──  Evidences
|
│   ├── Threat Data Sharing
│   │   └── Implement secure platforms for sharing threat intelligence and IOCs (Indicators of Compromise)
|		└──  Evidences
|
│   ├── Incident Response Planning
│   │   └── Align incident response plans with federal guidelines for information sharing
|		└──  Evidences
|
│   ├── Security Information Sharing Protocols
│   │   └── Use protocols such as STIX/TAXII for structured threat intelligence sharing
|		└──  Evidences
|
│   └── Data Retention Policies
│       └── Establish policies for retaining cybersecurity-related data in case of CISA investigations
|		└──  Evidences
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Network Monitoring and IDS/IPS
│   │   └── Use intrusion detection systems to capture relevant cybersecurity data for sharing
|		└──  Evidences
|		└──	 Tools
|			└── Snort + Snoby
|			└── SuriCata + Snoby
|			└── Wazuh
|			└── Zeek
|			└── SecurityOnion
|
│   ├── Logging and Monitoring
│   │   └── Ensure that cybersecurity incidents are logged and can be shared with CISA when required
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Data Encryption
│   │   └── Encrypt cybersecurity data before sharing with external agencies
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Secure Communication Channels
│   │   └── Use secure communication methods (e.g., VPNs, encrypted email) when sharing data
|		└──  Evidences
|		└──	 Tools
|			└── VPN -> OpenVPN, WireGuard, StrongSwan etc
|			└──	Traffic -> OpenSSL, Stunnel, Let's Encrypt etc
|			└── FileTransfer -> GnuPG, GPG etc
|
│   └── Data Sharing Infrastructure
│       └── Ensure that systems for sharing data with CISA are secure and compliant
|		└──  Evidences
|		└──	 Tools
|			└── GDrive with encrypted files
|			└── SFTP Servers
|			└── VeraCrypt
│
├── Threat Intelligence and Information Sharing
│   ├── Threat Intelligence Platforms (TIPs)
│   │   └── Implement platforms to aggregate and share threat intelligence with CISA and other entities
|		└──  Evidences
|		└──	 Tools
|			└── MISP
|			└── Cortex
|			└── TheHive
|			└── Yeti
|			└── IntelMQ
|
│   ├── Structured Threat Intelligence Formats
│   │   ├── STIX (Structured Threat Information eXpression)
│   │   └── TAXII (Trusted Automated eXchange of Indicator Information)
|		└──  Evidences
|		└──  Tools
|			└── MISP
|			└── OpenCTI
|
│   └── Indicators of Compromise (IOCs)
│       └── Share IOCs such as IP addresses, file hashes, and domains with CISA
|		└──  Evidences
|		└──  Tools
|			└── Leverage Logging Platforms
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with legal requirements for sharing threat information with CISA
    │   └── Maintain policies for protecting privacy and confidentiality when sharing data
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train employees on proper incident reporting procedures and data sharing policies
    │   └── Provide awareness training on cybersecurity threat intelligence sharing
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Ensure alignment with national cybersecurity strategies
        └── Encourage collaboration between public and private sectors for threat intelligence sharing
		└──  Evidences
```

### Checklist
https://www.cisa.gov/resources-tools/resources/cisa-cpg-checklist
https://www.cisa.gov/sites/default/files/publications/CISA_CPG_CHECKLIST_508c.pdf
https://cdn.ttgtmedia.com/rms/pdf/cisa_zero_trust_maturity_model_audit_checklist_download.pdf


### Policy Documentation Required

-   **Information Sharing Policy**
-   **Incident Reporting Policy**
-   **Breach Notification Policy**
-   **Threat Intelligence Sharing Policy**
-   **Access Control Policy**
-   **Data Protection and Anonymization Policy**
-   **Log Retention and Monitoring Policy**
-   **Third-Party Sharing Policy**


### Helpful Links
-   https://www.cisa.gov/publication/cybersecurity-best-practices-policies-and-procedures
-   https://www.sans.org/security-resources/policies/general/pdf/incident-response-policy
