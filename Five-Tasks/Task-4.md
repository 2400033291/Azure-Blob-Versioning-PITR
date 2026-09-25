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

## Procedure

### 1. Configure a Virtual Network

A Virtual Network was created to provide a private network environment for Azure resources.

The following configuration was used:

- **VNet Name:** `vnet-lab`
- **Address Space:** `10.0.0.0/16`
- **Subnet Name:** `subnet-vm`
- **Subnet Range:** `10.0.0.0/24`
- **DNS:** Azure-provided DNS

The Virtual Network was successfully created in the `rg-network-lab` Resource Group.

### 2. Configure the Subnet

The subnet `subnet-vm` was created inside the Virtual Network.

The subnet uses the address range:

```text
10.0.0.0/24
```

This subnet provides private IP addresses to resources deployed into it.

### 3. Deploy a Virtual Machine into the VNet

A Virtual Machine was deployed into the `vnet-lab` Virtual Network.

The VM configuration included:

- **VM Name:** `vm-network-lab`
- **Operating System:** Ubuntu Linux
- **Virtual Network:** `vnet-lab`
- **Subnet:** `subnet-vm`
- **Authentication:** SSH public key
- **Username:** `azureuser`

The VM was connected to the previously created Virtual Network and subnet.

### 4. Configure Private and Public IP Addresses

The VM network interface was configured with IP addressing.

The VM receives a **private IP address** from the `subnet-vm` address range for communication within the Virtual Network.

A **public IP address** was also associated with the VM to allow required external connectivity, such as SSH access.

The private and public IP addresses were verified through the VM networking configuration.

### 5. Configure Network Security Group

A Network Security Group named:

```text
nsg-vm
```

was used to control inbound and outbound network traffic for the VM.

An inbound rule allowing SSH traffic on port `22` was configured so that the VM could be accessed securely using SSH.

The Network Security Group was associated with the VM's network interface during deployment.

### 6. Configure Azure DNS Internal Name Resolution

The Virtual Network was configured to use **Azure-provided DNS**.

Azure-provided DNS can resolve Azure resource names within the Azure networking environment.

The DNS configuration was verified from the Virtual Network settings.

### 7. Configure External DNS Name Resolution

External DNS name resolution allows resources to resolve public domain names through DNS.

The VM can use DNS resolution for accessing external services and websites through its network connection.

Public DNS zone configuration was not required for the basic VM networking demonstration because no custom public domain was used in this practical.

## Final Configuration

- **Resource Group:** `rg-network-lab`
- **VNet:** `vnet-lab`
- **Address Space:** `10.0.0.0/16`
- **Subnet:** `subnet-vm`
- **Subnet Range:** `10.0.0.0/24`
- **VM:** `vm-network-lab`
- **NSG:** `nsg-vm`
- **DNS:** Azure-provided DNS
- **Private IP:** Assigned from the VNet subnet
- **Public IP:** Associated with the VM

## Result

The Virtual Network and subnet were successfully configured. A Virtual Machine was deployed into the VNet, and private and public IP addressing was configured.

A Network Security Group was configured to control network traffic, including SSH access. Azure-provided DNS was configured for name resolution.

## Conclusion

This task demonstrated Azure networking concepts including Virtual Networks, subnets, Virtual Machines, private and public IP addresses, Network Security Groups, and Azure DNS configuration.
