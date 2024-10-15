## ITIL (Information Technology Infrastructure Library)

```Tree Structure
├── Developer's Point of View (Application Security)
│   ├── Application Development Lifecycle
│   │   └── Align development processes with ITIL service design principles to ensure secure, reliable applications
|	|	└──  Evidences
|		└──  Tools
|			└── CI/CD Tools with Authentication and Authorisation or RBAC supported.
|
│   ├── Change and Release Management
│   │   └── Follow ITIL’s change management practices for deploying application updates securely
|	|	└──  Evidences
|		└──  Tools
|			└──  CI/CD Tools for Release Management
|			└── JIRA/Trello/Email/Slack for change management
|			└── GitHub ( ChangeLogs )
|
│   ├── Incident and Problem Management
│   │   └── Ensure that application issues are logged, tracked, and resolved in accordance with ITIL processes
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   ├── Service Design and Transition
│   │   └── Incorporate ITIL guidelines to ensure applications meet business requirements and security standards
|	|	└──  Evidences
|		└──  Tools
|			└── CI/CD Tools with Authentication and Authorisation or RBAC supported.
|
│   └── Continuous Improvement
│       └── Regularly review and enhance application performance based on ITIL’s continual service improvement (CSI) model
|	|	└──  Evidences
|		└──  Tools
|			└── CI/CD Tools with Authentication and Authorisation or RBAC supported.
|
│
├── IT Point of View (Operations and IT Management)
│   ├── Service Management and Delivery
│   │   └── Implement ITIL processes to manage the entire service lifecycle, from strategy to operation
|	|	└──  Evidences
|		└──  Tools
|			└── OTRS
|			└── GLPI
|			└── iTop
|			└── GLPI
|
│   ├── Incident, Problem, and Change Management
│   │   ├── Incident Management: Quickly resolve issues to restore normal operations.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster 			
|
│   │   ├── Problem Management: Identify and resolve root causes of recurring issues.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tools
|			└── Application Monitoring Tools ( Newrelic )
|			└── Infra monitoring tools
|			└── Container Monitoring tools
|
|
│   │   └── Change Management: Manage changes in IT systems to minimize risk and disruption.
|	|	└──  Evidences
|		└──  Tools
|			└── JIRA/Trello/Email to track change requests
|			└── Confluence/Coda/GoogleDoc/Github etc to maintain changelogs
|
│   ├── Configuration and Asset Management
│   │   └── Maintain accurate records of IT assets and their configurations in alignment with ITIL guidelines.
|	|	└──  Evidences
|		└──  Tools
|			 └── Cloud Native Asset Management Solutions
|			 └── SCM Tools ( Ansible, Chef, Puppet, Saltstack )
|			 └── IT Tools ( GLPI, iTOP, Snipe-IT, Ralph, OTRS ) 
|
│   ├── Service-Level Agreements (SLAs)
│   │   └── Define and manage SLAs to ensure IT services meet business needs and expectations.
|	|	└──  Evidences
|			└──  SLA Documentations
|			└──  SLA Dashboards/Reports
|
│   └── Capacity and Availability Management
│       └── Ensure IT resources are sufficient to meet demand, and that services are available when required.
|	|	└──  Evidences
│
├── Infrastructure Point of View (Network and System Security)
│   ├── Access and Identity Management
│   │   └── Manage user access rights and identity based on ITIL’s service operation guidelines.
|	|	└──  Evidences
|		└── Tools
|			└── MFA
|			└── KeyCloak
|			└── OpenIAM
|			└── Apache syncope
|			└── IAM ( Cloud Native )
|			└── RBAC ( role based access controls ) application native
|
│   ├── Network Monitoring and Performance
│   │   └── Implement monitoring tools to ensure network performance meets ITIL’s service-level requirements.
|	|	└──  Evidences
|		└── Tools
|			└── Cloud Native Network Monitoring ( Cloudwatch for AWS )
|			└── Icinga
|			└──  Zabbix
|			└──  PRTG Network Monitor
|			└──  Cacti
|			└──  Prometheus + Grafana
|
│   ├── Data Protection and Backup
│   │   └── Ensure secure data storage and regular backups according to ITIL’s availability management guidelines.
|	|	└──  Evidences
|		└── Tools
|			└── BorgBackup (Borg) 
|			└── Restic
|			└── Duplicity
|			└── Amanda (Advanced Maryland Automatic Network Disk Archiver)
|			└── Rclone
|			└── Rsnapshot
|			└── Velero (for Kubernetes backups)
|			└── Bacula
|			└── Snapshots ( Disk, DB Instances ) Cloud Native
|
│   ├── Incident Monitoring and Resolution
│   │   └── Use ITIL’s incident management framework to monitor and resolve infrastructure-related incidents.
|	|	└──  Evidences
|		└── Tools
|			└── Logging Tool ( for evidences ) + PagerDuty + JIRA 
|			└── XSOAR
|			└── Cortex + TheHive
|			└── Kolide 
|			└── GRR Rapid Response
|			└── SIEMonster
|
│   └── Vulnerability Management and Patching
│       └── Conduct regular system updates and patch management in alignment with ITIL’s change management processes.
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
│
├── ITIL Service Lifecycle
│   ├── Service Strategy
│   │   └── Align IT services with business goals and develop a strategy to manage service demand and cost.
|	|	└──  Evidences
|
│   ├── Service Design
│   │   └── Design new or updated services that meet current and future business requirements.
|	|	└──  Evidences
|		└──  Tools
|			└── draw.io
|			└── lucidchart.com
|
│   ├── Service Transition
│   │   └── Manage the deployment of services into production environments while minimizing risks.
|	|	└──  Evidences
|		└──  Tools
|			└── CI/CD tools with authentication & authorisation
|
│   ├── Service Operation
│   │   └── Ensure effective and efficient delivery of IT services on a day-to-day basis.
|	|	└──  Evidences
|
│   └── Continual Service Improvement (CSI)
│       └── Use metrics and feedback to improve the quality and performance of IT services continuously.
|	|	└──  Evidences
|		└──  Tools
|			 └── p99, p95 graph monitoring tools
|			 └── response time monitoring tools ( Newrelic, Datadog, Jaegar, VictoriaMetrics etc )
|
│
└── Other Perspectives
    ├── Legal and Compliance
    │   ├── Ensure that IT services comply with applicable legal and regulatory requirements.
    |	└──  Evidences
	|
    │   └── Implement ITIL’s governance framework to manage compliance and audit readiness
    ├── HR and Employee Training
    │   ├── Train IT staff on ITIL processes and service management best practices
    │   └── Provide ongoing education on ITIL’s service lifecycle and continual improvement methodologies
	|	└──  Evidences
	|
    └── Management and Leadership
        ├── Integrate ITIL principles into the organization’s IT governance and service management strategies
        ├── Ensure that leadership promotes ITIL adoption to improve service quality and efficiency
        └── Monitor service performance and align ITIL processes with business objectives
		└──  Evidences

```

### Checklist

* https://wiki.en.it-processmaps.com/index.php/ITIL-Checklists
* https://www.scribd.com/document/322737407/Checklist-of-Recommended-ITIL-Documents-for-Processes-and-Functions-En
* https://www.manageengine.com/products/service-desk/itsm/itil-best-practices.html
* https://info.advisera.com/20000academy/free-download/checklist-of-recommended-itil-documents-for-processes-and-functions


### Policy Documentation Required
-   **Service Management Policy**
-   **Change Management Policy**
-   **Incident Response and Management Plan**
-   **Problem Management Policy**
-   **Access Control and Identity Management Policy**
-   **Asset and Configuration Management Policy**
-   **Capacity and Availability Management Policy**
-   **Backup and Recovery Policy**
-   **Supplier Management Policy**

### Helpful Links
-   https://advisera.com/itilacademy/documentation/itil-toolkit/
-   https://www.itil-docs.com/templates/
