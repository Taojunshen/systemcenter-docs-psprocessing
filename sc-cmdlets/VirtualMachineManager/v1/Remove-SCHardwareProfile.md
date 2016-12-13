---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCHardwareProfile.md
schema: 2.0.0
ms.assetid: 147D988B-6A12-477B-8636-EA0FF74E19A8
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCHardwareProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCHardwareProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCHardwareProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCHardwareProfile

## SYNOPSIS
Removes a hardware profile object from the VMM library.

## SYNTAX

```
Remove-SCHardwareProfile [-HardwareProfile] <HardwareProfile> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCHardwareProfile** cmdlet removes one or more hardware profile objects from the VMM library.

This cmdlet returns the object upon success with the MarkedForDeletion property set to $True, or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific hardware profile from the library
```
PS C:\>$HWProfile = Get-SCHardwareProfile | where { $_.Name -eq "NewHWProfile01"}
PS C:\> Remove-SCHardwareProfile -HardwareProfile $HWProfile -Confirm
```

The first command gets the hardware profile object named NewHWProfile01 from the VMM library and stores the object in the $HWProfile variable.

The second command deletes NewHWProfle01 from the library, prompting the user for confirmation before completing the operation.

### Example 2: Remove all hardware profiles without being prompted to confirm each deletion
```
PS C:\>Get-SCHardwareProfile | Remove-SCHardwareProfile
```

This command gets all hardware profile objects in the library and passes each profile object to the **Remove-SCHardwareProfile** cmdlet, which removes each hardware profile.
By not using the *Confirm* parameter, you are not prompted to confirm whether to delete these hardware profile objects.

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

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
* Requires a VMM hardware profile object, which can be retrieved by using the Get-SCHardwareProfile cmdlet.

## RELATED LINKS

[Get-SCHardwareProfile](xref:VirtualMachineManager/v1/Get-SCHardwareProfile.md)

[New-SCHardwareProfile](xref:VirtualMachineManager/v1/New-SCHardwareProfile.md)

[Set-SCHardwareProfile](xref:VirtualMachineManager/v1/Set-SCHardwareProfile.md)

