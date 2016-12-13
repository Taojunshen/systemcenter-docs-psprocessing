---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceTemplate.md
schema: 2.0.0
ms.assetid: C1D7397F-2043-4A9B-BD30-2286EF55C645
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Resolve-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Resolve-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Resolve-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Resolve-SCServiceTemplate

## SYNOPSIS
Validates a service template and updates the global settings for the service template.

## SYNTAX

```
Resolve-SCServiceTemplate [-ServiceTemplate] <ServiceTemplate> [-Update] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Resolve-SCServiceTemplate** cmdlet validates a service template and updates the global settings for the service template.

## EXAMPLES

### Example 1: Validate the global settings in a service template
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01" | where { $_.Release -eq "Beta" }
PS C:\> Resolve-SCServiceTemplate -ServiceTemplate $SvcTemplate
```

The first command gets the Beta release of the service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The second command validates the global settings for the service template in $SvcTemplate and then displays the warnings (if any) for changes to the global settings.

### Example 2: Update the global settings in a specific service template
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01" | where { $_.Release -eq "Beta" }
PS C:\> Resolve-SCServiceTemplate -ServiceTemplate $SvcTemplate -Update
```

The first command gets the service template object that named ServiceTemplate01 with a release value of Beta and stores the object in the $SvcTemplate variable.

The second command updates the global settings for the service template stored in $SvcTemplate.

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

[Get-SCServiceTemplate](xref:VirtualMachineManager/v1/Get-SCServiceTemplate.md)

[New-SCServiceTemplate](xref:VirtualMachineManager/v1/New-SCServiceTemplate.md)

[Read-SCServiceTemplate](xref:VirtualMachineManager/v1/Read-SCServiceTemplate.md)

[Remove-SCServiceTemplate](xref:VirtualMachineManager/v1/Remove-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:VirtualMachineManager/v1/Set-SCServiceTemplate.md)

[Test-SCServiceTemplate](xref:VirtualMachineManager/v1/Test-SCServiceTemplate.md)

