# Lab 01 - Azure NAT Gateway

## Overview

This lab demonstrates how to configure Azure NAT Gateway to provide outbound Internet connectivity for a private Azure VM without assigning a public IP address.

## Objectives

After completing this lab, you will learn how to:

- Create an Azure Virtual Network
- Deploy a Linux VM without a public IP
- Create a NAT Gateway
- Associate NAT Gateway with a subnet
- Verify outbound Internet access

## Architecture

![Azure NAT Gateway Architecture](Azure-Administrator-AZ-104-Labs-2026/Diagrams/topology.png)

## Environment

| Resource | Name |
|----------|------|
| Resource Group | RG-NAT-LAB |
| Virtual Network | VNET-NAT |
| Subnet | PrivateSubnet |
| VM | UbuntuVM |
| NAT Gateway | NAT-GW |

## Lab Steps

### Step 1 - Create Resource Group

Explanation of the step.

Screenshot:

![Resource Group](Azure-Administrator-AZ-104-Labs-2026/Images/step01.png)


### Step 2 - Create Virtual Network

Explanation.

Screenshot:

![VNet](Azure-Administrator-AZ-104-Labs-2026/Images/step02.png)

### Step 3 - Deploy Linux VM

Explanation.

Command example:

```bash
az vm create \
--resource-group RG-NAT-LAB \
--name UbuntuVM
```
## Validation

Connect to the VM and run:
 ```bash
curl ifconfig.me
```
Expected result:
The returned public IP should be the NAT Gateway public IP.

## Cleanup

Delete the resource group:
 ```bash 
 az group delete \
   --name RG-NAT-LAB
 ```

## Key Takeaways

 - Azure NAT Gateway provides outbound Internet connectivity.
 - VMs keep private IP addresses.
 - Public IP exposure is avoided.

## References
