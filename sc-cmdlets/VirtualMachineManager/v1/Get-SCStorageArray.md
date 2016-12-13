---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCStorageArray.md
schema: 2.0.0
ms.assetid: 03B8E9B1-D947-4CA7-AA1A-9B8A736A59F3
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageArray.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageArray.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCStorageArray.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageArray

## SYNOPSIS
Gets a storage array object.

## SYNTAX

### All (Default)
```
Get-SCStorageArray [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### GetConnectableArray
```
Get-SCStorageArray -VMHost <Host[]> [-ConnectedToAllHost] [-FibreChannelOnly] [-iSCSIOnly] [-SASOnly]
 [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### GetStorageFileServerNodeArray
```
Get-SCStorageArray [-FibreChannelOnly] [-iSCSIOnly] [-SASOnly] [-VMMServer <ServerConnection>]
 [[-Name] <String>] -StorageFileServerNode <StorageFileServerNode[]> [<CommonParameters>]
```

### GetAssociatedWithHyperConvergedHostCluster
```
Get-SCStorageArray -HyperConvergedHostCluster <HostCluster> [-VMMServer <ServerConnection>] [[-Name] <String>]
 [<CommonParameters>]
```

### GetVmArray
```
Get-SCStorageArray [-VMMServer <ServerConnection>] [[-Name] <String>] -VM <VM[]> [<CommonParameters>]
```

### ID
```
Get-SCStorageArray [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageArray** cmdlet gets a storage array object from the Virtual Machine Manager (VMM) database.

You must install the storage provider on an available computer prior to discovering the storage resources.

For more information about configuring storage, see Configuring Storage in VMMhttp://go.microsoft.com/fwlink/?LinkID=212013 in the Microsoft TechNet library at http://go.microsoft.com/fwlink/?LinkID=212013.

## EXAMPLES

### Example 1: Get a storage array by its name
```
PS C:\>Get-SCStorageArray -Name "SANArray"
```

This command gets the storage array named SANArray.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectedToAllHost
Indicates that a storage array is connected to all hosts.

```yaml
Type: SwitchParameter
Parameter Sets: GetConnectableArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FibreChannelOnly
Indicates that only Fibre Channel arrays are returned.

```yaml
Type: SwitchParameter
Parameter Sets: GetConnectableArray, GetStorageFileServerNodeArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HyperConvergedHostCluster


```yaml
Type: HostCluster
Parameter Sets: GetAssociatedWithHyperConvergedHostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the unique ID identifier of the storage array that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the storage array that this cmdlet gets.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SASOnly
Indicates that only Shared Access Storage (SAS) storage arrays are returned.

```yaml
Type: SwitchParameter
Parameter Sets: GetConnectableArray, GetStorageFileServerNodeArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileServerNode
Specifies an array of storage file server node objects.

```yaml
Type: StorageFileServerNode[]
Parameter Sets: GetStorageFileServerNodeArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies an array of virtual machine objects.

```yaml
Type: VM[]
Parameter Sets: GetVmArray
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
Type: Host[]
Parameter Sets: GetConnectableArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -iSCSIOnly
Indicates that only iSCSI arrays are returned.

```yaml
Type: SwitchParameter
Parameter Sets: GetConnectableArray, GetStorageFileServerNodeArray
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageArray
This cmdlet returns a **StorageArray** object.

## NOTES

## RELATED LINKS

[Set-SCStorageArray](xref:VirtualMachineManager/v1/Set-SCStorageArray.md)

