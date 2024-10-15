## NIST (National Institute of Standards and Technology)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Software Development Lifecycle (SDLC)
│   │   └── Follow secure coding guidelines outlined in NIST SP 800-53 and SP 800-64
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
│   ├── Vulnerability Management
│   │   └── Regularly scan applications for vulnerabilities and apply fixes promptly
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├── Encryption and Data Protection
│   │   └── Use FIPS 140-2 validated cryptographic modules for protecting sensitive data
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Identity and Access Management
│   │   └── Implement Role-Based Access Control (RBAC) and multifactor authentication
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
│   └── Continuous Monitoring
│       └── Continuously monitor applications for security issues, using automated testing tools
|	|	└──  Evidences
|		└── Tools
|			└── OpenSCAP
|			└── Wazuh
|			└── Lynis
|			└── Scoutsuite
|			└── Prowler
|			└── Falco
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Risk Assessment and Management
│   │   └── Follow NIST Risk Management Framework (RMF) to assess, mitigate, and manage risks
|	|	└──  Evidences
|		└── Tools
|			└── OpenSCAP
|			└── Wazuh
|			└── Lynis
|			└── Scoutsuite
|			└── Prowler
|			└── Falco
|
│   ├── Incident Response Planning
│   │   └── Establish an incident response plan based on NIST SP 800-61 guidelines
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Continuous Monitoring
│   │   └── Implement continuous monitoring strategies in alignment with NIST SP 800-137
|	|	└──  Evidences
|		└──  Tools
|			 └── OpenSCAP
|			 └── Wazuh
|			 └── Lynis
|			 └── Scoutsuite
|			 └── Prowler
|			 └── Falco
|
│   ├── Access Control and Identity Management
│   │   └── Ensure that access controls follow NIST SP 800-53 guidelines, including least privilege
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
│   └── Audit and Reporting
│       └── Regularly audit IT systems and provide compliance reports based on NIST standards
|	|	└──  Evidences
|		└──  Tools
|			 └── OpenSCAP
|			 └── Wazuh
|			 └── Lynis
|			 └── Scoutsuite
|			 └── Prowler
|			 └── Falco
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Encryption and Key Management
│   │   └── Use FIPS 140-2 validated encryption for sensitive data in transit and at rest
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Ensure that network and system activities are logged and monitored per NIST guidelines
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Intrusion Detection and Prevention Systems (IDS/IPS)
│   │   └── Deploy and manage IDS/IPS systems to monitor network traffic for unauthorized activities
|	|	└──  Evidences
|		└──	 Tools
|			└── Snort + Snoby
|			└── SuriCata + Snoby
|			└── Wazuh
|			└── Zeek
|			└── SecurityOnion
|
│   ├── Network Security and Segmentation
│   │   └── Implement secure network architectures, including firewalls, VPNs, and DMZs
|	|	└──  Evidences
|		└──	 Tools
|			└── Firewall
|				└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|				└── Safeline
|				└── ModSecurity
|				└── Shadow Daemon 
|			└── VPN
|				└── OpenVPN
|				└── WireGuard
|				└── StrongSwan
|
│   └── Vulnerability Management
│       └── Regularly scan and patch network infrastructure to address vulnerabilities
|		└──  Evidences
|		└── Tools
|			└── Vulnerability_Management_Tools
|				└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|				└── Image Vulnerability -> Trivy, Grype, Clair
|				└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|				└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|				└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
├── NIST Frameworks and Guidelines
│   ├── NIST Cybersecurity Framework (CSF)
│   │   └── Align organizational security strategies with NIST’s Identify, Protect, Detect, Respond, Recover functions.
|	|	└──  Evidences
|
│   ├── NIST SP 800-53 (Security and Privacy Controls)
│   │   └── Implement and document security controls for federal information systems.
|	|	└──  Evidences
|
│   ├── NIST Risk Management Framework (RMF)
│   │   └── Implement a risk-based approach to securing information systems.
|	|	└──  Evidences
|
│   └── NIST SP 800-171 (Protecting Controlled Unclassified Information)
│       └── Apply guidelines for securing CUI in non-federal systems.
|	|	└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure that security controls meet NIST standards for federal and non-federal systems.
    │   └── Maintain compliance documentation for audits and regulatory purposes.
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Train employees on NIST cybersecurity frameworks and security controls
    │   └── Provide regular security awareness training based on NIST guidelines
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Align organizational goals with NIST cybersecurity principles
        ├── Ensure continuous evaluation and improvement of security practices per NIST
        └── Assign leadership to oversee NIST compliance and risk management activities.
		└──  Evidences
```

### Checklist

* https://nvlpubs.nist.gov/nistpubs/legacy/sp/nistspecialpublication800-100.pdf
* https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-70r3.pdf
* https://www.stqc.gov.in/sites/default/files/L1%20traceability%20matrix%20document.pdf

### Policy Documentation Required
-   **Information Security Policy**
-   **Risk Management Framework (RMF) Documentation**
-   **Incident Response Plan**
-   **Access Control Policy**
-   **Audit Log and Monitoring Policy**
-   **Change Management Policy**
-   **Configuration Management Policy**
-   **Contingency Planning (Disaster Recovery)**
-   **Physical Security Policy**
-   **Third-Party Service Provider Policy**


### Helpful Links
-   [https://www.nist.gov/cyberframework/framework](https://www.nist.gov/cyberframework/framework)
-   [https://csrc.nist.gov/publications/sp800](https://csrc.nist.gov/publications/sp800)
