## CIS Controls (Center for Internet Security)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Software Development
│   │   └── Follow secure coding standards based on CIS Control 16 (Application Software Security)
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
│   ├── Input Validation
│   │   └── Implement validation to protect against common vulnerabilities like SQL Injection (CIS Control 16.1)
|		└──  Evidences
| 		└── Tools
|			└── BurpSuite ( Pentest for Input Validation attacks such as SQL injections, XSS, XXE, Command Injection, Script Injection etc )
|
│   ├── Code Auditing and Testing
│   │   └── Conduct regular code reviews and penetration testing (CIS Control 16.4)
|		└──  Evidences
| 		└── Tools
|			└── DScanner ( BlackArch )
|			└── Any SAST Tool mentioned above.
|
│   ├── Application Whitelisting
│   │   └── Ensure that only approved applications are allowed to execute (CIS Control 2)
|		└──  Evidences
|		└── Tools 
|			└── SCM tools
|				└── Chef, Puppet, Saltstack, Ansible
|				└── Terraform ( userdata )
|				└── Golden Images ( Self Baked AMIs with approved applications )
|
│   └── Data Protection
│       └── Encrypt sensitive data at rest and in transit, adhering to encryption standards (CIS Control 13)
|		└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
│
├── IT Point of View (Operations and IT Management)
│   ├── Asset Inventory and Control
│   │   └── Maintain an inventory of hardware and software assets (CIS Control 1 and 2)
|		└──  Evidences
|		└── Tools
|			└── Cloud Native Asset Inventory ( AWS, GCP, Azure, OCI etc )
|			└── SnipeIT
|			└── Ralph3
|			└── AssetTiger
|			└── ResourceSpace
|
│   ├── Vulnerability Management
│   │   └── Regularly scan for and remediate vulnerabilities (CIS Control 3)
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├── Continuous Monitoring
│   │   └── Monitor IT systems for unauthorized changes and security issues (CIS Control 6)
|		└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OSSEC
|			└── Lynis
|			└── SuriCata
|
│   ├── Incident Response
│   │   └── Develop and maintain an incident response plan to address security incidents (CIS Control 19)
|		└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   └── Patch Management
│       └── Ensure timely application of security patches to reduce vulnerabilities (CIS Control 3.4)
|		└──  Evidences
|		└── Tools
|			└── Cloud Native Patch Management System ( AWS, GCP, Azure )
|			└── Heimdall Patch Management ( 30 days free trial )
|			└── PDQ Deploy ( windows patch management )
|			└── Comodo
|			└── Miradore
|			└── SCM tools ( Chef, Puppet, Saltstack, Ansible )
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Network Segmentation and Firewalls
│   │   └── Implement network segmentation and restrict traffic flows (CIS Control 12)
|		└──  Evidences
| 		└── Tools
|			└── Cloud Native WAFs ( AWS WAF, GCP Cloud Armor, Azure Defender )
|			└── Safeline
|			└── ModSecurity
|			└── Shadow Daemon 
|
│   ├── Data Encryption
│   │   └── Use encryption to protect sensitive information in transit and at rest (CIS Control 13)
|		└──  Evidences
|		└── Tools
| 			└── mTLS ( mutual TLS ) for data in transit.
|			└── SSL/TLS at Loadbalancers, proxies for data in transit
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Access Control and Authentication
│   │   └── Implement strong access controls and multifactor authentication (CIS Control 4)
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
│   ├── Logging and Monitoring
│   │   └── Log security events and retain logs for monitoring and auditing (CIS Control 6 and 8)
|		└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   └── Secure Configuration Management
│       └── Maintain secure configurations for servers, workstations, and network devices (CIS Control 5)
|		└──  Evidences
| 		└── Tools
|			└── OpenSCAP
|			└── Lynis
|			└── InSpec
|			└── Rudder
|			└── CfEngine
│
├── CIS Controls Categories
│   ├── Basic Controls
│   │   ├── Inventory and Control of Hardware Assets
│   │   ├── Inventory and Control of Software Assets
│   │   ├── Continuous Vulnerability Management
│   │   ├── Controlled Use of Administrative Privileges
│   │   └── Secure Configuration for Hardware and Software
|		└──  Evidences
|
│   ├── Foundational Controls
│   │   ├── Email and Web Browser Protections
│   │   ├── Malware Defenses
│   │   ├── Limitation and Control of Network Ports
│   │   └── Data Recovery Capability
|		└──  Evidences
|
│   └── Organizational Controls
│       ├── Security Awareness and Training
│       ├── Incident Response and Management
│       └── Penetration Testing
|		└──  Evidences
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure compliance with data protection regulations using CIS security controls
    │   └── Maintain documentation for audits and regulatory compliance
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Implement ongoing security awareness training (CIS Control 17)
    │   └── Ensure employees are trained on secure handling of sensitive information and access management
    |	└──  Evidences
	|
    └── Management and Leadership
        ├── Align organizational security policies with CIS Controls to reduce risks
        ├── Monitor and assess security control effectiveness regularly
        └── Promote a culture of cybersecurity awareness and proactive threat management
		└──  Evidences
```

### Checklist
* https://blackpointcyber.com/wp-content/uploads/2024/04/blackpoint-cis-controls-checklist.pdf
* https://downloads.cisecurity.org/#/


### Policy Documentation Required

-   **Information Security Policy**
-   **Vulnerability Management Policy**
-   **Access Control Policy**
-   **Data Encryption and Protection Policy**
-   **Incident Response Policy**
-   **Asset Inventory Policy**
-   **Audit Log and Monitoring Policy**
-   **Patch Management Policy**
-   **Penetration Testing Policy**
-   **Third-Party Risk Management Policy**

### Helpful Links
-   https://www.cisecurity.org/controls/
-   https://www.sans.org/security-resources/policies/general/pdf/security-policy
- https://www.diligent.com/resources/blog/what-is-cis-compliance
- https://www.algosec.com/resources/cis-compliance
