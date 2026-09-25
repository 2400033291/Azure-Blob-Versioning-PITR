# Task 1 – Azure PowerShell and Managed Disk

## Objective

To start an Azure PowerShell session in Azure Cloud Shell, create a Resource Group and Azure Managed Disk using Azure PowerShell, and configure the managed disk.

## Resources Created

- **Resource Group:** `rg-powershell-lab`
- **Region:** East Asia
- **Managed Disk:** `lab-managed-disk`
- **Initial Disk Size:** 32 GB
- **Final Disk Size:** 64 GB
- **Disk Type:** Standard_LRS

## Procedure

### 1. Verify Azure PowerShell Context

The Azure PowerShell session was started using Azure Cloud Shell.

The active Azure subscription was verified using:

```powershell
Get-AzContext
```

### 2. Create Resource Group

The following command was used to create the Resource Group:

```powershell
New-AzResourceGroup -Name "rg-powershell-lab" -Location "eastasia"
```

The Resource Group `rg-powershell-lab` was successfully created in the East Asia region.

### 3. Create Managed Disk Configuration

The managed disk configuration was created using:

```powershell
$diskConfig = New-AzDiskConfig `
    -Location "eastasia" `
    -CreateOption Empty `
    -DiskSizeGB 32 `
    -SkuName "Standard_LRS"
```

This configuration specified an empty 32 GB Standard_LRS managed disk.

### 4. Create the Managed Disk

The managed disk was created using:

```powershell
New-AzDisk `
    -ResourceGroupName "rg-powershell-lab" `
    -DiskName "lab-managed-disk" `
    -Disk $diskConfig
```

The managed disk was successfully created.

### 5. Configure the Managed Disk

The created disk was retrieved using:

```powershell
$disk = Get-AzDisk `
    -ResourceGroupName "rg-powershell-lab" `
    -DiskName "lab-managed-disk"
```

The disk size was changed from 32 GB to 64 GB:

```powershell
$disk.DiskSizeGB = 64
```

The updated configuration was applied using:

```powershell
Update-AzDisk `
    -ResourceGroupName "rg-powershell-lab" `
    -DiskName "lab-managed-disk" `
    -Disk $disk
```

## Final Configuration

The final managed disk configuration was verified as:

- **Disk Name:** `lab-managed-disk`
- **Resource Group:** `rg-powershell-lab`
- **Region:** East Asia
- **Disk Size:** 64 GB
- **Disk SKU:** Standard_LRS
- **Disk State:** Unattached

## Result

The Resource Group and Azure Managed Disk were successfully created using Azure PowerShell. The managed disk was configured and its size was successfully increased from 32 GB to 64 GB.

## Conclusion

This task demonstrated the use of Azure PowerShell in Azure Cloud Shell to create and configure Azure resources. It also demonstrated how to modify the configuration of an Azure Managed Disk.
