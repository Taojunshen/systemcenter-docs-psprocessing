---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageFileShare.md
schema: 2.0.0
ms.assetid: 0F757F50-17DC-4E1A-9B9B-470251219450
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Repair-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Repair-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Repair-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Repair-SCStorageFileShare

## SYNOPSIS
Repairs a storage file share.

## SYNTAX

### RepairShareWithHost (Default)
```
Repair-SCStorageFileShare -VMHost <Host> -StorageFileShare <StorageFileShare> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RepairShareWithCluster
```
Repair-SCStorageFileShare -VMHostCluster <HostCluster> -StorageFileShare <StorageFileShare>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RepairShareWithLibrary
```
Repair-SCStorageFileShare -LibraryServer <LibraryServer> -StorageFileShare <StorageFileShare>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-SCStorageFileShare** cmdlet repairs a specified storage file share.

## EXAMPLES

### Example 1: Repair a storage file share by providing a virtual machine host
```
PS C:\>$FileShare = Get-SCStorageFileShare -Name "FileShare01"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> Repair-SCStorageFileShare -StorageFileShare $FileShare -VMHost $VMHost
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command repairs FileShare01.

## PARAMETERS

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

### -LibraryServer
Specifies a Virtual Machine Manager (VMM) library server object.

```yaml
Type: LibraryServer
Parameter Sets: RepairShareWithLibrary
Aliases: 

Required: True
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

### -StorageFileShare
Specifies a storage file share.

```yaml
Type: StorageFileShare
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: RepairShareWithHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: RepairShareWithCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageFileShare.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMHost.md)

[New-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Register-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/v1.0/Unregister-SCStorageFileShare.md)

