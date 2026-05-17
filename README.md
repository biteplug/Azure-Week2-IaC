🚀 Azure Infrastructure as Code (ARM Template Deployment)
📌 Project Overview

This project demonstrates Infrastructure as Code (IaC) using Azure Resource Manager (ARM) templates to deploy a complete cloud infrastructure environment. The deployment includes networking components, security configuration, and a Linux Virtual Machine.

The goal of this project is to move away from manual Azure portal provisioning and implement automated, repeatable, and scalable infrastructure deployment using JSON-based ARM templates and Azure CLI.

🏗️ Architecture Overview

The deployed infrastructure includes:

Virtual Network (VNet)
Subnet
Network Security Group (NSG)
Network Interface (NIC)
Public IP Address
Linux Virtual Machine (Ubuntu)



⚙️ Technologies Used
Microsoft Azure
Azure Resource Manager (ARM Templates)
Azure CLI
Linux (Ubuntu 22.04 LTS)
JSON (Infrastructure as Code)

# Azure Infrastructure as Code (ARM Template Deployment)

## Project Overview

This project demonstrates Infrastructure as Code (IaC) using Azure Resource Manager (ARM) templates to deploy a secure and functional cloud infrastructure environment in Microsoft Azure.

The deployment was fully automated using Azure CLI and ARM templates instead of manual portal-based provisioning.

---

# Objectives

* Learn ARM template structure
* Deploy Azure infrastructure using Infrastructure as Code
* Configure networking resources
* Implement security controls using NSG
* Deploy and connect to a Linux Virtual Machine
* Troubleshoot real-world Azure deployment issues

---

# Technologies Used

* Microsoft Azure
* Azure CLI
* ARM Templates (JSON)
* Ubuntu Linux 22.04 LTS
* SSH
* GitHub

---

# Infrastructure Components

The deployment includes:

* Virtual Machine (Ubuntu Linux)
* Virtual Network (VNet)
* Subnet
* Network Interface (NIC)
* Public IP Address
* Network Security Group (NSG)

---

# Architecture Diagram/Structure

🔄 Architecture Flow
Internet
   ↓
Public IP
   ↓
Network Security Group (NSG)
   ↓
Network Interface (NIC)
   ↓
Virtual Machine (Ubuntu Linux)
   ↓
Subnet
   ↓
Virtual Network (VNet)

![Architecture Diagram]
![alt text](<Azure Infrastructure Architecture.png>)

---

# Deployment Commands

## Login to Azure

```bash
az login
```

## Create Resource Group

```bash
az group create --name MyCanadaRG --location canadacentral
```

## Validate ARM Template

```bash
az deployment group validate --resource-group MyCanadaRG --template-file azuredeploy.json
```

## Deploy Infrastructure

```bash
az deployment group create --resource-group MyCanadaRG --template-file azuredeploy.json
```

---

# Security Configuration

The Network Security Group (NSG) was configured to allow inbound SSH access on port 22.

---

# Challenges Encountered

During deployment, several VM size and region availability restrictions were encountered:

* Standard_DS1_v2 unavailable
* Standard_B1s unavailable
* Capacity restrictions in multiple Azure regions

## Resolution

Available VM SKUs were identified using:

```bash
az vm list-skus --location canadacentral --resource-type virtualMachines --output table
```

A compatible VM size was selected:

```text
Standard_B2s_v2
```

Additionally, SSH connectivity initially failed because the Network Security Group (NSG) was not attached to the Network Interface (NIC). This was resolved by associating the NSG with the NIC.

---

# Successful Deployment Proof

## SSH Access

![SSH Success]
![alt text](<SSH into VM 1.png>)
![alt text](<SSH into VM 2.png>)

---

# Deployment Output

* Resource Group: MyCanadaRG
* Region: Canada Central
* VM Name: myVM
* VM Size: Standard_B2s_v2
* Public IP: 20.104.202.15
* Deployment Status: Succeeded

---

# Key Skills Demonstrated

* Infrastructure as Code (IaC)
* Azure ARM Templates
* Azure Networking
* Cloud Security
* Linux Administration
* SSH Connectivity
* Azure CLI Automation
* Troubleshooting and Debugging

---

# Author

Nnenna Ewa F. 
# Azure-Week2-IaC
Azure Infrastructure as Code project using ARM Templates
