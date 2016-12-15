---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageFileServer.md
schema: 2.0.0
ms.assetid: C5D35DEE-F343-449D-AFFF-968394B3EFAD
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCStorageFileServer

## SYNOPSIS
Adds or removes a storage file share from VMM management.

## SYNTAX

### ManageFileShares (Default)
```
Set-SCStorageFileServer [-StorageFileServer] <StorageFileServer> [-JobGroup <Guid>] [-Description <String>]
 [-RemoveStorageFileShareFromManagement <StorageFileShare[]>] [-AddDiskWitnessFromStoragePool <StoragePool>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddFileServerToCluster
```
Set-SCStorageFileServer -AddExistingComputer <String[]> [-StorageFileServer] <StorageFileServer>
 [-JobGroup <Guid>] [-Description <String>] [-SkipClusterValidation] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### RemoveFileServerFromCluster
```
Set-SCStorageFileServer -RemoveExistingComputer <StorageFileServerNode[]>
 [-StorageFileServer] <StorageFileServer> [-JobGroup <Guid>] [-Description <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EnableFileShareManagement
```
Set-SCStorageFileServer [-StorageFileServer] <StorageFileServer> [-JobGroup <Guid>] [-Description <String>]
 -AddStorageFileShareToManagement <StorageFileShare[]>
 [-StorageClassificationAssociation <StorageClassification[]>]
 [-RemoveStorageFileShareFromManagement <StorageFileShare[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### SetFileServer
```
Set-SCStorageFileServer [-StorageFileServer] <StorageFileServer> [-JobGroup <Guid>] [-Description <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageFileServer** cmdlet adds or removes a storage file share from Virtual Machine Manager (VMM) management.

## EXAMPLES

### Example 1: Add a storage file share to VMM management
```
PS C:\>$FileServer = Get-SCStorageFileServer -Name "FileServer01.Contoso.com"
PS C:\> $FileShare = Get-SCStorageFileShare -Name "FileShare01" 
PS C:\> Set-SCStorageFileServer -StorageFileServer $FileServer -AddStorageFileShareToManagement $FileShare
```

The first command gets the storage file server object named FileServer01 by using the Get-SCStorageFileServer cmdlet.
The command stores that object in the $FileServer variable.

The second command gets the storage file share object named FileShare01 by using the Get-SCStorageFileShare cmdlet.
The command stores that object in the $FileShare variable.

The last command brings FileShare01 under VMM management.

### Example 2: Remove a storage file share from VMM management
```
PS C:\>$FileServer = Get-SCStorageFileServer -Name "FileServer01.Contoso.com"
PS C:\> $FileShare = Get-SCStorageFileShare -Name "FileShare01" 
PS C:\> Set-SCStorageFileServer -StorageFileServer $FileServer -RemoveStorageFileShareFromManagement $FileShare
```

The first command gets the storage file server object named FileServer01, and then stores that object in the $FileServer variable.

The second command gets the storage file share object named FileShare01, and then stores that object in the $FileShare variable.

The last command removes FileShare01 from VMM management.

## PARAMETERS

### -AddDiskWitnessFromStoragePool
Specifies a storage pool object.

```yaml
Type: StoragePool
Parameter Sets: ManageFileShares
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddExistingComputer
Specifies an array of computers that this cmdlet adds.
Specify the fully qualified domain names (FQDN), NetBIOS names, or IP addresses of servers on the network that have an operating system.

```yaml
Type: String[]
Parameter Sets: AddFileServerToCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddStorageFileShareToManagement
Enables management of the specified storage file share through VMM.

```yaml
Type: StorageFileShare[]
Parameter Sets: EnableFileShareManagement
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage file server.

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
Specifies a variable in which job progress is tracked and stored.

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

### -RemoveExistingComputer
Specifies an array of computers that this cmdlet removes.
Specify FQDNs, NetBios names, or IP addresses of servers on the network that have an operating system.

```yaml
Type: StorageFileServerNode[]
Parameter Sets: RemoveFileServerFromCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveStorageFileShareFromManagement
Specifies an array of storage file shares that this cmdlet removes from VMM management.

```yaml
Type: StorageFileShare[]
Parameter Sets: ManageFileShares, EnableFileShareManagement
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

### -SkipClusterValidation
Indicates that this cmdlet skips cluster validation tests when it creates a cluster.

```yaml
Type: SwitchParameter
Parameter Sets: AddFileServerToCluster
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageClassificationAssociation
Specifies an array of storage classification objects that is associated with a storage pool.

```yaml
Type: StorageClassification[]
Parameter Sets: EnableFileShareManagement
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: ManageFileShares, EnableFileShareManagement
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: StorageFileServer
Parameter Sets: AddFileServerToCluster, RemoveFileServerFromCluster, SetFileServer
Aliases: 

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

### StorageFileServer
This cmdlet returns a **StorageFileServer** object.

## NOTES

## RELATED LINKS

[Get-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileServer.md)

[Install-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCStorageFileServer.md)

[Uninstall-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCStorageFileServer.md)

[Get-SCStorageFileShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileShare.md)
