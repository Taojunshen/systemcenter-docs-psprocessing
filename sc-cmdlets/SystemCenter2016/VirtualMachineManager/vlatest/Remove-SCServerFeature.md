---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCServerFeature.md
schema: 2.0.0
ms.assetid: 8E8DCC7F-3689-4D8F-B1EA-3CD2533D3DCF
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServerFeature.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServerFeature.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServerFeature.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCServerFeature

## SYNOPSIS
Removes an operating system role or feature from a guest operating system profile.

## SYNTAX

### OSProfile
```
Remove-SCServerFeature -ServerFeature <ServerFeature> -GuestOSProfile <GuestOSProfile> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Template
```
Remove-SCServerFeature -ServerFeature <ServerFeature> -VMTemplate <Template> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCServerFeature** cmdlet deletes an operating system role or feature from a guest operating system profile.

## EXAMPLES

### Example 1: Remove a server feature from a guest operating system profile
```
PS C:\>$OSProfile = Get-SCGuestOSProfile -Name "NewOSProfile01"
PS C:\> $Feature = Get-SCServerFeature -Name "Failover-Clustering" 
PS C:\> Remove-SCServerFeature -GuestOSProfile $OSProfile -ServerFeature $Feature
```

The first command gets the gues operating system profile named NewOSProfile01 and stores the object in the $OSProfile variable.

The second command gets the server feature object named Failover-Clustering and stores the object in the $Feature variable.

The last command removes the server feature stored in $Feature from the guest operating system profile stored in $OSProfile.

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

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
Parameter Sets: OSProfile
Aliases: 

Required: True
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

### -ServerFeature
Specifies a server feature object.

```yaml
Type: ServerFeature
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: 

Required: True
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

[Add-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCServerFeature.md)

[Get-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md)

[Get-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServerFeature.md)

