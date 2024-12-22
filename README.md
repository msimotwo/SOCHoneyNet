# SOCHoneyNet

# Implementing a SOC and Honeynet in Azure

This repository showcases the implementation of a Security Operations Center (SOC) and a Honeynet within the Azure ecosystem. The project demonstrates the use of Azure Virtual Machines, Microsoft Sentinel (SIEM), and Log Analytics to monitor and analyze suspicious activities.

## Overview

The purpose of this project is to:

1. Create a Honeynet to attract and monitor potential malicious activities.
2. Integrate Azure Virtual Machines as the environment for the honeypot systems.
3. Utilize Microsoft Sentinel to act as the central SIEM solution.
4. Leverage Log Analytics for detailed data aggregation and visualization.

---

## Architecture

The setup includes the following components:

- **Azure Virtual Machines**: Deployed as honeypot systems with basic configurations to mimic real-world environments.
- **Microsoft Sentinel**: Configured for log ingestion, analysis, and alerting.
- **Log Analytics Workspace**: Used to aggregate logs from the honeypot systems for detailed monitoring.

---

## Getting Started

### Prerequisites

- Azure account with sufficient permissions to deploy resources.
- Familiarity with Azure Portal and basic network/security concepts.
- Tools: Azure CLI, PowerShell (optional).

### Deployment Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/soc-honeynet-azure.git
   cd soc-honeynet-azure
   ```

2. **Deploy Azure Resources**
   Use the provided ARM template or Bicep file to deploy the necessary infrastructure.
   ```bash
   az deployment group create --resource-group <resource-group-name> --template-file deploy.json
   ```

3. **Configure Honeynet**
   - Deploy a Virtual Machine to act as the honeypot.
   - Install vulnerable services or simulate an application to attract malicious activity.

4. **Integrate Microsoft Sentinel**
   - Enable Sentinel in your Azure environment.
   - Link it to the Log Analytics Workspace.

5. **Set Up Log Analytics**
   - Configure data sources to collect logs from honeypot systems.
   - Create custom queries for monitoring and alerting.

---

## Key Features

- **Honeynet Implementation**: Attracts attackers to observe behaviors and analyze tactics.
- **Log Aggregation**: Centralized logging through Azure's Log Analytics Workspace.
- **Real-time Monitoring**: Microsoft Sentinel enables detection and alerting of suspicious activities.

---

## Queries and Dashboards

- **Sample KQL Query**: Retrieve failed login attempts.
   ```kql
   SecurityEvent
   | where EventID == 4625
   | summarize count() by Computer, Account
   ```

- **Custom Dashboard**: Visualize network traffic, failed logins, and other key metrics.

---

## Next Steps

- Fine-tune Sentinel rules for more precise detection.
- Enhance honeypot systems with additional vulnerabilities for diverse testing.
- Regularly review and analyze logs for new attack patterns.

---

## Contributing

Contributions are welcome! Feel free to submit issues or pull requests to enhance the project.


---

## Acknowledgments

Special thanks to the cybersecurity community for providing tools and inspiration for this project.
