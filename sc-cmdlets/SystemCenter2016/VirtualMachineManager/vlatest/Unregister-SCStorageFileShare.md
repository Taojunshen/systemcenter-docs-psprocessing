---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5981D221-6251-4E29-B100-9787B03D79E1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Unregister-SCStorageFileShare

## SYNOPSIS
Unregisters a storage file share from a VM host, cluster, or library server.

## SYNTAX

### UnregisterFromHost (Default)
```
Unregister-SCStorageFileShare [-StorageFileShare] <StorageFileShare> -VMHost <Host>
 [-RemovePermissionsFromShare] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UnregisterFromCluster
```
Unregister-SCStorageFileShare [-StorageFileShare] <StorageFileShare> -VMHostCluster <HostCluster>
 [-RemovePermissionsFromShare] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UnregisterFromLibrary
```
Unregister-SCStorageFileShare [-StorageFileShare] <StorageFileShare> -LibraryServer <LibraryServer>
 [-RemovePermissionsFromShare] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Unregister-SCStorageFileShare** cmdlet unregisters a storage file share from a virtual machine host, cluster, or library server.

## EXAMPLES

### Example 1: Unregister a storage file share from a library server
```
PS C:\> $FileShare = Get-SCStorageFileShare -Name "FileShare01" 
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibraryServer01.Contoso.com"
PS C:\> Unregister-SCStorageFileShare -StorageFileShare $FileShare -LibraryServer $LibServer
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command gets the VMM library server object named LibraryServer01 and stores the object in the $LibServer variable.

The last command unregisters FileShare01 from LibraryServer01.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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
Parameter Sets: UnregisterFromLibrary
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

### -RemovePermissionsFromShare
Indicates that permissions are removed from the file share.

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
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: UnregisterFromHost
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
Parameter Sets: UnregisterFromCluster
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

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileShare.md)

[New-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md)

[Register-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md)

