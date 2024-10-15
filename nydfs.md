## NYDFS (New York Department of Financial Services Cybersecurity Regulation)

```Tree structure
├ Developer's Point of View (Application Security)
│   ├ Secure Application Development
│   │   └── Ensure that applications handling financial or personal data comply with NYDFS cybersecurity requirements
|	|	└──  Evidences
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
│   ├ Encryption and Data Protection
│   │   └── Encrypt sensitive financial data both in transit and at rest (NYDFS Section 500.15)
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├ Multi-Factor Authentication (MFA)
│   │   └── Implement MFA for applications accessing non-public information (NYDFS Section 500.12)
|	|	└──  Evidences
|		└──	 Tools
|			 └── Google Authenticator
|			 └── privacyIDEA
|			 └── Keycloak
|			 └── Duo
|
│   ├ Secure Access to Customer Data
│   │   └── Ensure strong access controls are implemented for users accessing financial and personal data
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
│   └── Logging and Auditing
│       └── Ensure that applications log access to sensitive data for auditing and compliance purposes.
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│
├ IT Point of View (Operations and IT Management)
│   ├ Access Control and Identity Management
│   │   └── Enforce identity and access management protocols to protect sensitive data (NYDFS Section 500.07).
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
│   ├ Incident Response and Breach Notification
│   │   └── Establish a cybersecurity incident response plan and notify the NYDFS within 72 hours of a breach (NYDFS Section 500.17).
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├ Risk Assessment
│   │   └── Conduct regular risk assessments to identify and mitigate cybersecurity threats (NYDFS Section 500.09).
|	|	└──  Evidences
|		└── Tools
|			└── OpenVAS
|			└── OwaspZAP
|			└── Wazuh
|			└── Nessus/Scoutsuite/Prowler
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├ Data Encryption
│   │   └── Use encryption for non-public information in transit and at rest (NYDFS Section 500.15).
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   └── Continuous Monitoring and Vulnerability Management
│       └── Implement continuous monitoring and vulnerability scanning of systems handling sensitive data (NYDFS Section 500.05).
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├ Encryption and Data Protection
│   │   └── Encrypt sensitive financial data and personally identifiable information (PII) at rest and during transmission (NYDFS Section 500.15).
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├ Network Security and Segmentation
│   │   └── Implement secure network segmentation and firewalls to protect systems from unauthorized access (NYDFS Section 500.02).
|	|	└──  Evidences
|		└──  Tools
|			 └── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|
│   ├ Access Control
│   │   └── Enforce role-based access controls for systems that handle non-public information (NYDFS Section 500.07).
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
│   ├ Logging and Monitoring
│   │   └── Implement logging and monitoring for systems handling sensitive data, with audit logs retained for compliance (NYDFS Section 500.06).
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   └── Vulnerability and Patch Management
│       └── Regularly assess vulnerabilities in critical systems and apply patches to mitigate risks (NYDFS Section 500.07).
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
├ NYDFS Cybersecurity Framework
│   ├ Cybersecurity Program
│   │   └── Develop and maintain a cybersecurity program to protect sensitive data and ensure compliance (NYDFS Section 500.02).
|	|	└──  Evidences
|
│   ├ Cybersecurity Policy
│   │   └── Create and enforce policies to manage cybersecurity risks, aligned with business operations (NYDFS Section 500.03).
|	|	└──  Evidences
|
│   ├ Chief Information Security Officer (CISO)
│   │   └── Designate a CISO to oversee the organization’s cybersecurity program and report to senior leadership (NYDFS Section 500.04).
|	|	└──  Evidences
|
│   ├ Risk-Based Authentication
│   │   └── Implement risk-based authentication measures, including MFA, for accessing sensitive data (NYDFS Section 500.12).
|	|	└──  Evidences
|		└──	 Tools
|			 └── Google Authenticator
|			 └── privacyIDEA
|			 └── Keycloak
|			 └── Duo
|
│   └── Third-Party Service Provider Security
│       └── Ensure that third-party vendors comply with the organization’s cybersecurity requirements (NYDFS Section 500.11).
|	|	└──  Evidences
|
│
└── Other Perspectives
    ├ Legal and Compliance
    │   ├ Ensure that financial institutions comply with the NYDFS cybersecurity regulation for safeguarding non-public information.
    │   └── Maintain documentation for audits and submit annual certification of compliance to NYDFS (NYDFS Section 500.17)
	|	└──  Evidences
	|
    ├ HR and Employee Training
    │   ├ Provide training for employees on the NYDFS cybersecurity requirements, data protection practices, and incident response
    │   └── Conduct ongoing security awareness programs focused on protecting non-public information
	|	└──  Evidences
	|
    └── Management and Leadership
        ├ Assign leadership to oversee NYDFS cybersecurity compliance and risk management efforts
        ├ Ensure continuous improvement of the cybersecurity program and regular risk assessments
        └── Involve senior management in reviewing cybersecurity reports and incident response strategies
		└──  Evidences
```



### Checklist

* https://kybersecure.com/wp-content/uploads/2017/12/Kyber_NYDFS-Security-Checklist.pdf
* https://www.prevalent.net/content-library/nydfs-23-nycrr-500-compliance-checklist/
* https://secureframe.com/blog/nydfs-nycrr-500
* https://www.dfs.ny.gov/system/files/documents/2023/10/rf_fs_2amend23NYCRR500_text_20231101.pdf
* https://securitycheckbox.com/control-frameworks/


### Policy Documentation Required* Cybersecurity Program Documentation
* Cybersecurity Policy
* Incident Response Plan
* Risk Assessment Documentation
* Access Control and Identity Management Policy
* Data Encryption Policy
* Audit Log and Monitoring Policy
* Third-Party Vendor Management Policy
* Penetration Testing and Vulnerability Management Policy



### Helpful Links
* https://advisera.com/27001academy/nydfs-cybersecurity-compliance/
* https://www.sans.org/security-resources/policies/general/pdf/information-security-policy


