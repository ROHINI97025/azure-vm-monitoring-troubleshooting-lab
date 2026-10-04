# Azure VM Monitoring & Troubleshooting Lab

## Project Overview

This project demonstrates a basic Azure VM environment with networking, secure remote access, and VM monitoring.

The lab was created to practice Azure administration and troubleshooting concepts using an Ubuntu virtual machine.

## Azure Services Used

- Azure Virtual Machine
- Azure Virtual Network (VNet)
- Subnet
- Network Security Group (NSG)
- SSH
- Azure Monitor
- Azure Metrics
- Azure Monitor Alert Rules

## What I Configured

- Created an Azure resource group for the lab.
- Created an Ubuntu 24.04 LTS virtual machine.
- Configured a VNet and subnet for the VM.
- Configured an NSG with SSH access on port 22.
- Connected to the Linux VM successfully using SSH.
- Created an Azure Monitor alert for high CPU usage.
- Configured the alert for average CPU usage above 80% over 5 minutes.
- Monitored VM CPU usage using Azure Metrics.

## Testing

To test VM monitoring, CPU load was intentionally increased on the Ubuntu VM.

The Azure Metrics page recorded CPU usage of approximately **85%+**, confirming that the CPU monitoring metric was working.

The alert rule was configured successfully, although a fired-alert instance was not retained in the alert history during the test window.

## Troubleshooting Scenario

### Scenario: VM Connectivity Check

When connecting to the Linux VM, the following areas were verified:

1. VM was running.
2. VNet and subnet were configured.
3. NSG allowed SSH traffic on port 22.
4. The VM had a public IP address.
5. SSH authentication using the private key was successful.

This demonstrated a basic Azure VM connectivity troubleshooting process.

## Architecture

```text
Azure
│
└── Resource Group
    │
    ├── Virtual Network
    │   └── Subnet
    │       └── Ubuntu VM
    │           └── Network Interface
    │
    └── Network Security Group
        └── SSH (TCP 22)

Azure Monitor
└── Percentage CPU
    └── High CPU Alert (>80%)
```

## Screenshots

### VM Overview
![VM Overview](screenshots/01-vm-overview.png)

### VNet and Subnet
![Networking](screenshots/02-networking-vnet-subnet.png)

### NSG Rules
![NSG Rules](screenshots/03-nsg-rules.png)

### SSH Connection
![SSH Connection](screenshots/04-SSH-connection.png)

### CPU Monitoring
![CPU Metric](screenshots/05-CPU-metric-85-percent.png)

### Alert Rule
![Alert Rule](screenshots/06-alert-rule.png)

## Key Learning

This project provided hands-on practice with Azure VM networking, VNet and subnet configuration, NSG rules, SSH access, Azure Monitor metrics, alert configuration, and basic troubleshooting.

## Cleanup

After completing the lab and testing, the resource group was deleted to avoid unnecessary Azure resource usage and charges.
