---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalNetworkDefinition.md
schema: 2.0.0
ms.assetid: 32E56010-D54B-4ABF-B056-FB5387B5B4C5
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLogicalNetworkDefinition.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLogicalNetworkDefinition.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLogicalNetworkDefinition.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLogicalNetworkDefinition

## SYNOPSIS
Deletes a logical network definition.

## SYNTAX

```
Remove-SCLogicalNetworkDefinition [-VMMServer <ServerConnection>]
 [-LogicalNetworkDefinition] <LogicalNetworkDefinition> [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLogicalNetworkDefinition** cmdlet deletes a logical network definition (also called a network site).

## EXAMPLES

### Example 1: Delete a logical network definition
```
PS C:\>$Definition = Get-SCLogicalNetworkDefinition -Name "Logical Network Definition 01"
PS C:\> Remove-SCLogicalNetworkDefinition -LogicalNetworkDefinition $Definition
```

The first command gets the logical network definition named "Logical Network Definition 01" and stores it in the $Definition variable.

The second command deletes the logical network definition stored in the $Definition variable.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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
Specifies the name of a variable that you use to track and store job progress.

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

### -LogicalNetworkDefinition
Specifies a logical network definition (also called a network site) that contains the subnet that the IP address pool serves, as specified by the *Subnet* parameter.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies a Virtual Machine Manager (VMM) server object.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LogicalNetworkDefiniton
This cmdlet returns a **LogicalNetworkDefiniton** object.

## NOTES
* Requires a VMM logical network definition object, which can be retrieved by using the Get-SCLogicalNetworkDefinition cmdlet.

## RELATED LINKS

[Get-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCLogicalNetworkDefinition.md)

[New-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCLogicalNetworkDefinition.md)

[Set-SCLogicalNetworkDefinition](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCLogicalNetworkDefinition.md)

