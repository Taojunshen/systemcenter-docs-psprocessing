---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageVolume.md
schema: 2.0.0
ms.assetid: 3C3A796C-064E-43B4-8AFC-508445985598
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageVolume.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageVolume.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageVolume.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageVolume

## SYNOPSIS
Modifies the setting for a volume on a host that enables VMM to evaluate that volume as available storage during the virtual machine placement process.

## SYNTAX

```
Set-SCStorageVolume [-StorageVolume] <StorageVolume> [-AvailableForPlacement <Boolean>]
 [-DedupMode <DedupMode>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageVolume** cmdlet modifies the setting that determines whether Virtual Machine Manager (VMM) evaluates a specific volume on a host server as available storage during the virtual machine placement process.

During the placement process, VMM evaluates managed hosts, including the volumes on those managed hosts, when calculating a recommendation for the best location on which to deploy a virtual machine.
If you specify that a volume on the host will not be included when VMM performs its automatic placement calculation, you can still choose to manually deploy a virtual machine on that volume.

## EXAMPLES

### Example 1: Make a volume on a host available for placement
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> $StorageVol = Get-SCStorageVolume -VMHost $VMHost
PS C:\> Set-SCStorageVolume -StorageVolume $StorageVol[0] -AvailableForPlacement $True
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the storage volume object for the host stored in $VMHost and then stores the object in the $StorageVol variable.
This example assumes that VMHost01 has only one volume.

The last command makes the first volume object on VMHost01 available for placement.
Setting the parameter AvailableForPlacement to $True enables the VMM placement process to evaluate this volume on VMHost01 as a possible candidate to host virtual machines.

### Example 2: Make a second volume on a host available for placement
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost02.Contoso.com"
PS C:\> $StorageVols = Get-SCStorageVolume -VMHost $VMHost 
PS C:\> Set-SCStorageVolume -StorageVolume $StorageVols[1] -AvailableForPlacement $True
```

The first command gets the host object named VMHost02 and stores the object in the $VMHost variable.

The second command gets all storage volume objects VMHost02 and stores the objects in the object array named $StorageVols.
This example assumes that VMHost02 has at least two volumes.

The last command makes the second volume stored in the $StorageVols array available for placement.

## PARAMETERS

### -AvailableForPlacement
Indicates whether the VMM placement process considers this host or this volume on a host to be eligible as a possible location on which to deploy virtual machines.
If this parameter is set to $False, you can choose to deploy virtual machines on this host or volume anyway.
The default value is $True.
This parameter does not apply to VMware ESX hosts.

When you use this parameter with network adapters, if set to $False, then placement does not consider the logical networks configured on this network adapter to determine if the host is suitable for connecting a virtual machine.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DedupMode
Apply deduplication on the volume or file share based on the workload.
The acceptable values for this parameter are:

- 0 - Disabled 
- 1 - GeneralPurpose 
- 2 - Hyper-V
- 3 - Backup

```yaml
Type: DedupMode
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, GeneralPurpose, HyperV, Backup, NotAvailable

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageVolume
Specifies a storage volume object on a specific virtual machine host.

```yaml
Type: StorageVolume
Parameter Sets: (All)
Aliases: VMHostVolume

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageVolume
This cmdlet returns a **StorageVolume** object.

## NOTES

## RELATED LINKS

[Get-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageVolume.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHost.md)

[New-SCStorageVolume](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageVolume.md)

