---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceTemplate.md
schema: 2.0.0
ms.assetid: 37962A0A-2D03-43F0-A61D-0B2EABE612C8
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCServiceTemplate

## SYNOPSIS
Validates a service template and stores any errors in the ValidationErrors property of the service template.

## SYNTAX

```
Test-SCServiceTemplate [-ServiceTemplate] <ServiceTemplate> [-Update] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCServiceTemplate** cmdlet validates a service template and stores the errors in the ValidationErrors property of the service template.

## EXAMPLES

### Example 1: Validate a service template
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01" | where { $_.Release -eq "Beta" }
PS C:\> $UpdatedSvcTemplate = Test-SCServiceTemplate -ServiceTemplate $SvcTemplatePS C:\> $UpdatedSvcTemplate.ValidationErrors[0]
```

The first command gets the Beta release of the service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The second command validates the service template in $SvcTemplate.

The third command displays the first validation error for service template from the validation error array.

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

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Update
Updates the settings for an object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ServiceTemplate
This cmdlet returns a **ServiceTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServiceTemplate.md)

[New-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCServiceTemplate.md)

[Read-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCServiceTemplate.md)

[Remove-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCServiceTemplate.md)

[Resolve-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Resolve-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCServiceTemplate.md)

