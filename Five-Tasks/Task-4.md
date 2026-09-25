# Task 4 – Virtual Network, VM, IP Address, NSG, and DNS Configuration

## Objective

To configure an Azure Virtual Network, deploy a Virtual Machine into the VNet, configure private and public IP addresses, configure a Network Security Group, and configure Azure DNS name resolution.

## Resources Created

- **Resource Group:** `rg-network-lab`
- **Region:** East Asia
- **Virtual Network:** `vnet-lab`
- **VNet Address Space:** `10.0.0.0/16`
- **Subnet:** `subnet-vm`
- **Subnet Address Range:** `10.0.0.0/24`
- **Network Security Group:** `nsg-vm`
- **Virtual Machine:** `vm-network-lab`
- **Operating System:** Ubuntu Server 24.04 LTS
- **Username:** `azureuser`

## Procedure

### 1. Configure a Virtual Network

A Virtual Network was created to provide a private network environment for Azure resources.

The following configuration was used:

- **VNet Name:** `vnet-lab`
- **Address Space:** `10.0.0.0/16`
- **Subnet Name:** `subnet-vm`
- **Subnet Range:** `10.0.0.0/24`
- **DNS:** Azure-provided DNS

The Virtual Network was created in the `rg-network-lab` Resource Group.

### 2. Configure the Subnet

The subnet `subnet-vm` was created inside the Virtual Network.

The subnet uses the address range:

```text
10.0.0.0/24
```

This subnet provides private IP addresses to resources deployed into the Virtual Network.

### 3. Deploy a Virtual Machine into the VNet

A Virtual Machine named `vm-network-lab` was deployed into the existing Virtual Network.

The VM configuration included:

- **VM Name:** `vm-network-lab`
- **Operating System:** Ubuntu Server 24.04 LTS
- **Virtual Network:** `vnet-lab`
- **Subnet:** `subnet-vm`
- **Authentication:** SSH public key
- **Username:** `azureuser`

The VM was successfully deployed into the `vnet-lab` Virtual Network and `subnet-vm` subnet.

### 4. Configure Private and Public IP Addresses

The VM network interface was configured with IP addressing.

The VM receives a **private IP address** from the `subnet-vm` address range for communication within the Virtual Network.

A **public IP address** named `vm-network-lab-ip` was associated with the VM to provide external network connectivity and SSH access.

The private and public IP addresses were verified through the VM networking configuration.

### 5. Configure Network Security Group

A Network Security Group named:

```text
nsg-vm
```

was associated with the VM network interface.

An inbound rule allowing SSH traffic on port `22` was configured to permit SSH access to the Ubuntu VM.

The Network Security Group controls inbound and outbound network traffic for the VM.

### 6. Configure Azure DNS Internal Name Resolution

The Virtual Network was configured to use **Azure-provided DNS**.

Azure-provided DNS supports name resolution for Azure resources within the Azure networking environment.

The DNS configuration was verified through the Virtual Network settings.

### 7. Configure External DNS Name Resolution

The VM has internet connectivity through its public network configuration and can use DNS resolution to access external websites and services.

A custom public Azure DNS zone was not created because no custom domain name was required for this practical.

## Final Configuration

- **Resource Group:** `rg-network-lab`
- **VNet:** `vnet-lab`
- **Address Space:** `10.0.0.0/16`
- **Subnet:** `subnet-vm`
- **Subnet Range:** `10.0.0.0/24`
- **VM:** `vm-network-lab`
- **Operating System:** Ubuntu Server 24.04 LTS
- **NSG:** `nsg-vm`
- **Public IP:** `vm-network-lab-ip`
- **DNS:** Azure-provided DNS
- **Private IP:** Assigned from the VNet subnet

## Result

The Virtual Network and subnet were successfully configured. A Virtual Machine was deployed into the VNet, and private and public IP addressing was configured.

A Network Security Group was configured to control network traffic, including SSH access. Azure-provided DNS was configured for name resolution.

## Conclusion

This task demonstrated Azure networking concepts including Virtual Networks, subnets, Virtual Machines, private and public IP addresses, Network Security Groups, and Azure DNS configuration.
