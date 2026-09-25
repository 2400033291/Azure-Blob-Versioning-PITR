# Task 3 – Resource Deployment, Resource Movement, and Resource Lock

## Objective

To deploy a resource into an existing Resource Group, move the resource between Resource Groups, and implement and test a Resource Lock using Azure.

## Resources Used

- **Original Resource Group:** `rg-powershell-lab`
- **Destination Resource Group:** `rg-powershell-lab-moved`
- **Resource:** `lab-managed-disk`
- **Resource Type:** Azure Managed Disk
- **Lock Name:** `lab-disk-lock`
- **Lock Type:** CanNotDelete

## Procedure

### 1. Deploy Resource to an Existing Resource Group

The managed disk created in Task 1 was initially deployed into the existing Resource Group:

```powershell
rg-powershell-lab
```

The managed disk used for this task was:

```text
lab-managed-disk
```

The resource was successfully available in the Resource Group.

### 2. Create Destination Resource Group

A second Resource Group was used as the destination for moving the managed disk:

```text
rg-powershell-lab-moved
```

The destination Resource Group was created in the East Asia region.

### 3. Move Resource Between Resource Groups

The managed disk `lab-managed-disk` was moved from:

```text
rg-powershell-lab
```

to:

```text
rg-powershell-lab-moved
```

After the move, the resource was verified in the destination Resource Group.

### 4. Implement Resource Lock

A delete lock was created on the managed disk using Azure PowerShell.

The following command was used:

```powershell
New-AzResourceLock `
    -LockName "lab-disk-lock" `
    -LockLevel CanNotDelete `
    -ResourceGroupName "rg-powershell-lab-moved" `
    -ResourceName "lab-managed-disk" `
    -ResourceType "Microsoft.Compute/disks"
```

The `CanNotDelete` lock prevents the protected resource from being deleted while the lock is applied.

### 5. Verify Resource Lock

The lock was verified using:

```powershell
Get-AzResourceLock `
    -ResourceGroupName "rg-powershell-lab-moved" `
    -ResourceName "lab-managed-disk" `
    -ResourceType "Microsoft.Compute/disks"
```

The `lab-disk-lock` resource lock was displayed successfully.

### 6. Test the Resource Lock

A deletion operation was attempted on the protected managed disk.

The operation was stopped at the confirmation prompt, demonstrating the protection provided by the resource lock.

The resource was not deleted.

### 7. Remove the Resource Lock

After completing the test, the resource lock was removed.

The lock was first retrieved using:

```powershell
$lock = Get-AzResourceLock `
    -ResourceGroupName "rg-powershell-lab-moved" `
    -ResourceName "lab-managed-disk" `
    -ResourceType "Microsoft.Compute/disks"
```

The lock was then removed using:

```powershell
Remove-AzResourceLock -LockId $lock.LockId -Force
```

The managed disk remained available after the lock was removed.

## Final Configuration

- **Original Resource Group:** `rg-powershell-lab`
- **Destination Resource Group:** `rg-powershell-lab-moved`
- **Resource:** `lab-managed-disk`
- **Lock Name:** `lab-disk-lock`
- **Lock Level:** CanNotDelete
- **Lock Test:** Completed
- **Lock Removed:** Yes

## Result

The managed disk was successfully moved from one Resource Group to another. A `CanNotDelete` resource lock was successfully created and verified. The lock was tested and subsequently removed after the practical demonstration.

## Conclusion

This task demonstrated Azure Resource Group management, resource movement between Resource Groups, and the use of Resource Locks to protect Azure resources from accidental deletion.
