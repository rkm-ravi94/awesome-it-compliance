## NERC CIP (North American Electric Reliability Corporation Critical Infrastructure Protection)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Secure Software Development
│   │   └── Ensure development practices meet security requirements for critical infrastructure systems
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
│   ├── Access Control
│   │   └── Implement role-based access control in applications handling critical infrastructure data (CIP-004)
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
│   ├── Data Integrity and Confidentiality
│   │   └── Ensure that applications protect the integrity and confidentiality of sensitive infrastructure data
|	|	└──  Evidences
|		└── Tools ( File Integrity )
|			└── Wazuh
|			└── TripWire
|			└── Aide
|			└── Samhain
|			└── Snoopy Logger
|
│   ├── Incident Response
│   │   └── Ensure that applications can log and track security incidents for response purposes (CIP-008)
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   └── Logging and Auditing
│       └── Implement logging mechanisms to capture and retain user activities for compliance and audits (CIP-007)
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Personnel Training and Security Awareness
│   │   └── Implement training programs to educate staff on security procedures 
for critical infrastructure (CIP-004)
|	|	└──  Evidences
|
│   ├── Access Control and Identity Management
│   │   └── Enforce strict access control policies for systems that handle critical infrastructure data (CIP-005)
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
│   ├── Incident Reporting and Response
│   │   └── Establish incident response protocols and reporting mechanisms in line with NERC CIP requirements (CIP-008)
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Configuration Management and Change Control
│   │   └── Ensure that changes to critical systems are managed and tracked through a formal process (CIP-010)
|	|	└──  Evidences
|		└── Tools 
|			└── SCM tools
|				└── Chef, Puppet, Saltstack, Ansible
|				└── OpenSCAP, Packer
|				└── Terraform ( userdata )
|				└── Golden Images ( Self Baked AMIs with approved applications )
|
│   └── Monitoring and Auditing
│       └── Implement continuous monitoring and auditing of critical infrastructure systems (CIP-007)
|		└──  Evidences
|		└── Tools
|			└── OpenSCAP
|			└── Wazuh
|			└── Lynis
|			└── Scoutsuite
|			└── Prowler
|			└── Falco
|
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Network Security and Segmentation
│   │   └── Implement network segmentation to protect critical infrastructure systems from external threats (CIP-005)
|	|	└──  Evidences
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
│   ├── Data Encryption
│   │   └── Use encryption to protect data transmitted between critical infrastructure systems (CIP-011)
|	|	└──  Evidences
|		└──	 Tools
|			└── OpenSSL/LibreSSL (FIPS 140-2 module enabled)
|			└── Libgcrypt ( for customer managed encryption )
|			└── StrongSwan/OpenVPN/Pritunl (IPsec VPN for Secure Transit )
|			└── GnuTLS ( mTLS based comms )
|			└── KMS, CMEK, x509, Cloud Native Encryption ( AWS, GCP, Azure, OCI etc provides Data Encryption at Rest which can be used by enabling encryption flags for certain resources such as EBS, DISKs, Volumes, RDS etc )
|
│   ├── Logging and Monitoring
│   │   └── Log all access to critical systems and monitor logs for security incidents (CIP-007)
|	|	└──  Evidences
|		└── Tools
|			└── ELK Setup ( Elasticsearch, Logstash, Kibana, Filebeat/FluentD/Fluentbit )
|			└── LOKI ( Prometheus Stack )
| 			└── GrayLog
|			└── SigNoz
|			└── Splunk ( prebuilt filters )
|
│   ├── Vulnerability and Patch Management
│   │   └── Regularly assess vulnerabilities and apply patches to critical infrastructure systems (CIP-007)
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   └── Physical Security Controls
│       └── Implement physical access controls and monitoring for critical infrastructure facilities (CIP-006)
|		└──  Evidences
|		└── Tools
|			└── Thales Luna HSM devices ( Physical Server Vault )
|			└── ZoneMinder/Motion (for video surveillance)
│			└── Security Onion/Nagios/MeshCentral ( for monitoring based on Sensors )
|
│
├── NERC CIP Compliance Controls
│   ├── CIP-002: Critical Cyber Asset Identification
│   │   └── Identify and classify critical cyber assets that support bulk electric systems
|	|	└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   ├── CIP-003: Security Management Controls
│   │   └── Implement security management controls for protecting critical cyber assets.
|	|	└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   ├── CIP-004: Personnel and Training
│   │   └── Ensure personnel handling critical infrastructure systems are trained and cleared for access
|	|	└──  Evidences
|
│   ├── CIP-005: Electronic Security Perimeters
│   │   └── Define and implement electronic security perimeters for critical infrastructure systems.
|	|	└──  Evidences
|		└── Tools
|			└── Wazuh
|			└── OWASP ZAP
|			└── Lynis
|			└── OpenSCAP
|			└── Scout Suite
|			└── Prowler
|
│   ├── CIP-006: Physical Security of BES Cyber Systems
│   │   └── Implement physical security measures to protect critical cyber systems from physical threats.
|	|	└──  Evidences
|
│   ├── CIP-007: Systems Security Management
│   │   └── Implement system security controls, including patch management and monitoring.
|	|	└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│   ├── CIP-008: Incident Reporting and Response Planning
│   │   └── Establish an incident response plan for identifying, reporting, and resolving security incidents.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── CIP-009: Recovery Plans for BES Cyber Systems
│   │   └── Develop recovery plans for critical infrastructure systems in case of outages or disasters.
|	|	└──  Evidences
|
│   └── CIP-010: Configuration Change Management and Vulnerability Assessments
│       └── Manage system configurations and perform regular vulnerability assessments.
|		└──  Evidences
|		└── Tools
|			└── Code Vulenrabitlity -> SCA, SAST Tools discussed above
|			└── Image Vulnerability -> Trivy, Grype, Clair
|			└── VM Vulnerability -> Wazuh, Lynis, Lunar, OpenSCAP
|			└── Cloud Misconfig/CSPM -> ScoutSuite, Prowler, CS Suite
|			└── K8s/EKS/AKS/GKE -> Kube-Bench, KubeAudit, Kube-Hunter
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure all systems comply with NERC CIP guidelines and report compliance to regulatory bodies
    │   └── Maintain documentation and records for audits and compliance reviews.
	|	└──  Evidences
	|
    ├── HR and Employee Training
    │   ├── Provide training to personnel on the requirements of NERC CIP and their roles in protecting critical infrastructure
    │   └── Ensure that only cleared and trained personnel have access to critical cyber systems.
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Appoint security leadership responsible for NERC CIP compliance and risk management
        ├── Ensure continuous improvement and adaptation of security controls for critical infrastructure systems
        └── Regularly audit and assess the organization’s compliance with NERC CIP standards
		└──  Evidences
```

### Checklist

* https://assets.website-files.com/5ffef4c69be53b44bd10b438/6012f587cd82e75440411439_NERC-CIP%20Compliance%20Checklist.pdf
* https://www.nerc.com/comm/PC/Synchronized%20Measurement%20Subcommittee/pnnl_26874_cip_recomm_synchrophasors_20170926.pd.pdf
* https://www.se.com/us/en/download/document/PAS_63680_CPM16119/


### Policy Documentation Required
-   **Cyber Security Policy**
-   **Incident Response Plan**
-   **Access Control Policy**
-   **Physical Security Policy**
-   **Change Management Policy**
-   **Configuration Management Policy**
-   **Audit and Logging Policy**
-   **Training and Awareness Policy**
-   **Recovery Plan for Critical Infrastructure**

### Helpful Links
-   https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx
-   https://complianceforge.com/nerc-cip-compliance/
