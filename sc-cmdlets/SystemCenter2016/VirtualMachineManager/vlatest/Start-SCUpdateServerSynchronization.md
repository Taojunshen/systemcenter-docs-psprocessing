---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUpdateServer.md
schema: 2.0.0
ms.assetid: 3C64D469-EDD4-4F0B-BE41-72D408670677
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateServerSynchronization.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateServerSynchronization.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCUpdateServerSynchronization.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCUpdateServerSynchronization

## SYNOPSIS
Starts syncrhronization between a VMM update server and WSUS.

## SYNTAX

```
Start-SCUpdateServerSynchronization [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 [-ForceFullUpdateCatalogImport] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCUpdateServerSynchronization** cmdlet starts synchronization between the Virtual Machine Manager (VMM) update server and Windows Server Update Services (WSUS).

The first time this synchronization runs, it imports the full WSUS update catalog into VMM.
By default, after the first synchronization, this cmdlet performs an incremental import.
To force a full catalog import, specify the *ForceFullUpdateCatalogImport* parameter.

## EXAMPLES

### Example 1: Start an update server synchronization
```
PS C:\>$UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
PS C:\> Start-SCUpdateServerSynchronization -UpdateServer $UpdateServer
```

The first command gets the update server named WSUSComputer01, and then stores that object in the $UpdateServer variable.

The second command starts synchronization between WSUSComputer01 and Microsoft Update.

### Example 2: Start a full import of the Microsoft Update Catalog
```
PS C:\>$UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
PS C:\> Start-SCUpdateServerSynchronization -UpdateServer $UpdateServer -ForceFullUpdateCatalogImport
```

The first command gets the update server named WSUSComputer01, and then stores that object in the $UpdateServer variable.

The second command starts synchronization between WSUSComputer01 and Microsoft Update.
The command specifies that the full catalog is imported.

## PARAMETERS

### -ForceFullUpdateCatalogImport
Indicates that the VMM update server imports the full update catalog from WSUS.
By default, after the first synchronization, this cmdlet performs an incremental import.

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

### -UpdateServer
Specifies a VMM update server that this cmdlet synchronizes to WSUS.

```yaml
Type: UpdateServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server for which this cmdlet synchronizes the VMM update server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### UpdateServer
This cmdlet returns an **UpdateServer** object.

## NOTES

## RELATED LINKS

[Get-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md)

