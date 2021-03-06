---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C49EA8B3-3A8F-493E-A0D6-4D62107F2756
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCStorageFileServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCStorageFileServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCStorageFileServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Uninstall-SCStorageFileServer

## SYNOPSIS
Destroys a file server cluster.

## SYNTAX

### RemoveNodes
```
Uninstall-SCStorageFileServer -StorageFileServer <StorageFileServer>
 -RemoveExistingComputer <StorageFileServerNode[]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UninstallByStorageFileServerObject
```
Uninstall-SCStorageFileServer -StorageFileServer <StorageFileServer> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Uninstall-SCStorageFileServer** cmdlet destroys a specified file server cluster.

## EXAMPLES


## PARAMETERS

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
Specify fully qualified domain names (FQDN), NetBIOS names, or IP addresses of servers on the network that have an operating system.

```yaml
Type: StorageFileServerNode[]
Parameter Sets: RemoveNodes
Aliases: 

Required: True
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

### -StorageFileServer
Specifies a storage file server object.

```yaml
Type: StorageFileServer
Parameter Sets: RemoveNodes
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: StorageFileServer
Parameter Sets: UninstallByStorageFileServerObject
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

### StorageFileServer
This cmdlet returns a **StorageFileServer** object.

## NOTES

## RELATED LINKS

[Get-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFileServer.md)

[Install-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCStorageFileServer.md)

[Set-SCStorageFileServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServer.md)

