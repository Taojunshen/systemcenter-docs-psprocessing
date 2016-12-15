---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCGuestOSProfile.md
schema: 2.0.0
ms.assetid: 9F64783B-5E0F-47FD-AF55-B4F784C19997
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCGuestOSProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCGuestOSProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCGuestOSProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCGuestOSProfile

## SYNOPSIS
Removes a guest operating system profile object from VMM.

## SYNTAX

```
Remove-SCGuestOSProfile [-GuestOSProfile] <GuestOSProfile> [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCGuestOSProfile** cmdlet removes one or more guest operating system profile objects from the VMM library.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific guest operating system profile from the library
```
PS C:\>$OSProfile = Get-SCGuestOSProfile -Name "NewOSProfile01"
PS C:\> Remove-SCGuestOSProfile -GuestOSProfile $OSProfile -Confirm
```

The first command gets the guest operating system profile object named NewOSProfile01 and stores the object in the $OSProfile variable.

The second command removes the guest operating system profile stored in $OSProfile, prompting for confirmation before completing the operation.

### Example 2: Remove all operating system profiles without being prompted to confirm each deletion
```
PS C:\>$OSProfiles = Get-SCGuestOSProfile -VMMServer "VMMServer01.Contoso.com"
PS C:\> $OSProfiles | Remove-SCGuestOSProfile
```

The first command gets all operating system profile objects from VMMServer01 and stores the objects in the $OSProfiles object array.

The second command passes each object in $OSProfiles to the Remove-OSProfile cmdlet, which removes each of the guest operating system profile objects from the VMM library.

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

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
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
* Requires a VMM guest operating system profile object, which can be retrieved by using the Get-SCGuestOSProfile cmdlet.

## RELATED LINKS

[Get-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md)

[New-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCGuestOSProfile.md)

[Set-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestOSProfile.md)

