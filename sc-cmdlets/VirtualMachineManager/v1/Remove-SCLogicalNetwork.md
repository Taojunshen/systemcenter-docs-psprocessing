---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalNetwork.md
schema: 2.0.0
ms.assetid: 948F920D-35FF-4DF6-9C1E-B870E8D7A402
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLogicalNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLogicalNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCLogicalNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLogicalNetwork

## SYNOPSIS
Deletes a logical network object.

## SYNTAX

```
Remove-SCLogicalNetwork [-VMMServer <ServerConnection>] [-LogicalNetwork] <LogicalNetwork> [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLogicalNetwork** cmdlet deletes a Virtual Machine Manager (VMM) logical network object.

If any logical network definition, virtual machine template, or service template object references a specific logical network object, that logical network object is not deleted.

## EXAMPLES

### Example 1: Delete a logical network
```
PS C:\>$LogicalNetwork = Get-SCLogicalNetwork "LogicalNetwork01"
PS C:\> Remove-SCLogicalNetwork -LogicalNetwork $LogicalNetwork
```

The first command gets the logical network object named LogicalNetwork01 and stores it in the $LogicalNetwork variable.

The second command deletes the logical network object stored in $LogicalNetwork.

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

### -LogicalNetwork
Specifies a logical network.
A logical network is a named grouping of IP subnets and virtual local area networks (VLANs) that is used to organize and simplify network assignments.

```yaml
Type: LogicalNetwork
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

### LogicalNetwork
This cmdlet returns a **LogicalNetwork** object.

## NOTES
* Requires a VMM logical network object, which you can retrieve by using the Get-SCLogicalNetwork cmdlet.

## RELATED LINKS

[Get-SCLogicalNetwork](xref:VirtualMachineManager/v1/Get-SCLogicalNetwork.md)

[New-SCLogicalNetwork](xref:VirtualMachineManager/v1/New-SCLogicalNetwork.md)

[Set-SCLogicalNetwork](xref:VirtualMachineManager/v1/Set-SCLogicalNetwork.md)

