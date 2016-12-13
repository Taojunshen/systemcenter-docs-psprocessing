---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceTemplate.md
schema: 2.0.0
ms.assetid: 6CDF859F-D30C-46AB-917F-F05B563E8550
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCServiceTemplate

## SYNOPSIS
Refreshes the properties of a service template and displays the updates in the VMM console.

## SYNTAX

```
Read-SCServiceTemplate [-ServiceTemplate] <ServiceTemplate> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCServiceTemplate** cmdlet refreshes the properties of a service template and reflects the updates in the Virtual Machine Manager (VMM) console.

## EXAMPLES

### Example 1: Refresh a specified service template object
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -VMMServer "VMMServer01.Contoso.com" -Name "ServiceTemplate01"
PS C:\> Read-SCServiceTemplate -ServiceTemplate $SvcTemplate
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The second command refreshes the properties of the service template stored in $SvcTemplate.

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

[Remove-SCServiceTemplate](xref:VirtualMachineManager/v1/Remove-SCServiceTemplate.md)

[Resolve-SCServiceTemplate](xref:VirtualMachineManager/v1/Resolve-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:VirtualMachineManager/v1/Set-SCServiceTemplate.md)

[Test-SCServiceTemplate](xref:VirtualMachineManager/v1/Test-SCServiceTemplate.md)

