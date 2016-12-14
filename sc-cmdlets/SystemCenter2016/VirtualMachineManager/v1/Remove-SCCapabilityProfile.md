---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCapabilityProfile.md
schema: 2.0.0
ms.assetid: 4BA0AF44-C60A-44F7-B0AD-3070818B5A81
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCapabilityProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCapabilityProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCCapabilityProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCCapabilityProfile

## SYNOPSIS
Deletes a capability profile from VMM.

## SYNTAX

```
Remove-SCCapabilityProfile [-CapabilityProfile] <CapabilityProfile> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCCapabilityProfile** cmdlet deletes a capability profile from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Delete a specific capability profile
```
PS C:\>$CapabilityProfile = Get-SCCapabilityProfile -Name "CapabilityProf01"
PS C:\> Remove-SCCapabilityProfile -CapabilityProfile $CapabilityProfile -Confirm
```

The first command gets the capability profile object named CapabilityProf01 and stores the object in the $CapabilityProfile variable.

The second command deletes the capability profile stored in $CapabilityProfile (CapabilityProf01), prompting you for confirmation before performing the operation.

## PARAMETERS

### -CapabilityProfile
Specifies a capability profile object.

```yaml
Type: CapabilityProfile
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
* Requires a VMM capability profile object, which can be retrieved using the Get-SCCapabilityProfile cmdlet.

## RELATED LINKS

[Get-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCCapabilityProfile.md)

[New-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCCapabilityProfile.md)

[Set-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCCapabilityProfile.md)

[Test-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Test-SCCapabilityProfile.md)

