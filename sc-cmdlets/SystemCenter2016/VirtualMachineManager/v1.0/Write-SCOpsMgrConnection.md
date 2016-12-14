---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCOpsMgrConnection.md
schema: 2.0.0
ms.assetid: A24D4B5B-62FC-4515-84E1-4DD167CEE1A9
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Write-SCOpsMgrConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Write-SCOpsMgrConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Write-SCOpsMgrConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Write-SCOpsMgrConnection

## SYNOPSIS
Updates Operations Manager with the most current information from VMM.

## SYNTAX

```
Write-SCOpsMgrConnection [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Write-SCOpsMgrConnection** cmdlet updates Operations Manager with the most current information from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Update VMM data in Operations Manager
```
PS C:\>Write-SCOpsMgrConnection
```

This command updates Operations Manager with the most current data from VMM.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### OpsMgrConnection
This cmdlet returns an **OpsMgrConnection** object.

## NOTES

## RELATED LINKS

[Get-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCOpsMgrConnection.md)

[New-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCOpsMgrConnection.md)

[Remove-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCOpsMgrConnection.md)

[Set-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCOpsMgrConnection.md)

