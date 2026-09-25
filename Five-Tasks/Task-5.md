# Task 5 – Azure VM, Storage Account, Blob Storage, Authentication, and Azure Files

## Objective

To deploy an Azure Virtual Machine, configure an Azure Storage Account, manage blob storage, configure storage authentication and authorization, and create an Azure Files share.

## Resources Used

- **Resource Group:** `rg-network-lab`
- **Virtual Machine:** `vm-network-lab`
- **Storage Account:** `blobrestoreproject2026`
- **Blob Container:** `project-data`
- **Blob:** `travel-data.txt`
- **Azure Files Share:** `lab-fileshare`

## Procedure

### 1. Deploy an Azure VM

An Azure Virtual Machine named `vm-network-lab` was deployed in the `rg-network-lab` Resource Group.

The VM was configured with:

- **Operating System:** Ubuntu Server 24.04 LTS
- **Authentication:** SSH public key
- **Username:** `azureuser`
- **Virtual Network:** `vnet-lab`
- **Subnet:** `subnet-vm`
- **Public IP:** `vm-network-lab-ip`
- **Network Security Group:** `nsg-vm`

The VM was successfully deployed and connected to the configured Virtual Network.

### 2. Create and Configure a Storage Account

The existing Azure Storage Account:

```text
blobrestoreproject2026

was used for the practical.

The storage account provides blob storage and file storage services.

The account was configured with:

Performance: Standard
Redundancy: Locally Redundant Storage (LRS)
3. Manage Blob Storage

A private blob container named:

project-data

was used to store the project data.

The blob:

travel-data.txt

was created and managed inside the container.

Blob Versioning was enabled to maintain previous versions of the blob.

Blob Soft Delete and Container Soft Delete were also configured to protect against accidental deletion.

The blob was modified and previous versions were verified to demonstrate data recovery.

4. Configure Storage Authentication and Authorization

A Shared Access Signature (SAS) was generated for the storage account.

The SAS was configured with restricted access permissions.

The configuration included:

Allowed Service: Blob
Resource Types: Service, Container, Object
Permissions: Read and List
Protocol: HTTPS only
IP Restriction: Not specified
Signing Key: key1
Limited Validity Period: Configured

The SAS provides controlled and time-limited access to Azure Storage resources without exposing the storage account key.

5. Create and Configure Azure Files Share

An Azure Files share named:

lab-fileshare

was created in the storage account.

The file share was configured with:

Share Name: lab-fileshare
Access Tier: TransactionOptimized
Protocol: SMB

The file share provides cloud-based file storage that can be accessed using the SMB protocol.

Final Configuration
Component	Configuration
VM	vm-network-lab
Storage Account	blobrestoreproject2026
Blob Container	project-data
Blob	travel-data.txt
SAS Authentication	Generated
Azure Files Share	lab-fileshare
File Protocol	SMB
File Access Tier	TransactionOptimized
Result

The Azure Virtual Machine was successfully deployed.

The Azure Storage Account and blob storage were configured and used for storing project data.

Storage access was controlled using a Shared Access Signature with restricted permissions and HTTPS-only access.

An Azure Files share was also successfully created using the SMB protocol.

Conclusion

This task demonstrated Azure Virtual Machine deployment, Azure Storage Account configuration, blob management, secure storage access using SAS, and Azure Files configuration.
