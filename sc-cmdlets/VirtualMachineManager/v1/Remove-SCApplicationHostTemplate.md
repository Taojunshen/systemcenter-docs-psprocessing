---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCApplicationHostTemplate.md
schema: 2.0.0
ms.assetid: 6D6056F0-4888-4CFF-A580-57181A98B59E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationHostTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationHostTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationHostTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCApplicationHostTemplate

## SYNOPSIS
Removes an application host template from a service template.

## SYNTAX

```
Remove-SCApplicationHostTemplate [-ApplicationHostTemplate] <ApplicationHostTemplate> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCApplicationHostTemplate** cmdlet removes an application host template from a service template.

## EXAMPLES

### Example 1: Remove an application host template from a service template
```
PS C:\>$ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $AppHostTemplate = Get-SCApplicationHostTemplate -ServiceTemplate $ServiceTemplate
PS C:\> Remove-SCApplicationHostTemplate -ApplicationHostTemplate $AppHostTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the application host template object for the service template in $ServiceTemplate and stores the object in the $AppHostTemplate variable.

The last command removes the application host template in $AppHostTemplate.

## PARAMETERS

### -ApplicationHostTemplate
Specifies an application host template object.

```yaml
Type: ApplicationHostTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

## NOTES

## RELATED LINKS

[Add-SCApplicationHostTemplate](xref:VirtualMachineManager/v1/Add-SCApplicationHostTemplate.md)

[Get-SCApplicationHostTemplate](xref:VirtualMachineManager/v1/Get-SCApplicationHostTemplate.md)

[Get-SCServiceTemplate](xref:VirtualMachineManager/v1/Get-SCServiceTemplate.md)

[Set-SCApplicationHostTemplate](xref:VirtualMachineManager/v1/Set-SCApplicationHostTemplate.md)

