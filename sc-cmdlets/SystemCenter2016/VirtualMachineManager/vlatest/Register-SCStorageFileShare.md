---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6DCF9218-A288-40BD-BECB-7A24578E5BA5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Register-SCStorageFileShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Register-SCStorageFileShare

## SYNOPSIS
Registers a storage file share with a VM host, cluster, or library server.

## SYNTAX

### RegisterToHost (Default)
```
Register-SCStorageFileShare -VMHost <Host> -FileSharePath <String> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterShareToHost
```
Register-SCStorageFileShare -VMHost <Host> -StorageFileShare <StorageFileShare> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterShareToCluster
```
Register-SCStorageFileShare -VMHostCluster <HostCluster> -StorageFileShare <StorageFileShare>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToCluster
```
Register-SCStorageFileShare -VMHostCluster <HostCluster> -FileSharePath <String> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterShareToLibrary
```
Register-SCStorageFileShare -LibraryServer <LibraryServer> -StorageFileShare <StorageFileShare>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RegisterToLibrary
```
Register-SCStorageFileShare -LibraryServer <LibraryServer> -FileSharePath <String> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCStorageFileShare** cmdlet registers a storage file share with a virtual machine host, cluster, or library server.

## EXAMPLES

### Example 1: Register a storage file share with a library server
```
PS C:\> $FileShare = Get-SCStorageFileShare -Name "FileShare01" 
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibraryServer01.Contoso.com"
PS C:\> Register-SCStorageFileShare -StorageFileShare $FileShare -LibraryServer $LibServer
```

The first command gets the storage file share object named FileShare01 and stores the object in the $FileShare variable.

The second command gets the VMM library server object named LibraryServer01 and stores the object in the $LibServer variable.

The last command registers FileShare01 with LibraryServer01.

## PARAMETERS

### -FileSharePath
Specifies the path to the file share.

```yaml
Type: String
Parameter Sets: RegisterToHost, RegisterToCluster, RegisterToLibrary
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: RegisterShareToLibrary, RegisterToLibrary
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
Parameter Sets: RegisterShareToHost, RegisterShareToCluster, RegisterShareToLibrary
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

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: RegisterToHost, RegisterShareToHost
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
Parameter Sets: RegisterShareToCluster, RegisterToCluster
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

### StorageFileShare
This cmdlet returns a **StorageFileShare** object.

## NOTES

## RELATED LINKS

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileShare.md)

[New-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFileShare.md)

[Remove-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFileShare.md)

[Repair-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCStorageFileShare.md)

[Set-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileShare.md)

[Unregister-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Unregister-SCStorageFileShare.md)

