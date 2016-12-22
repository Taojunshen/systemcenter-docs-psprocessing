---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3C028D37-3153-4C18-B90C-564AD1A04E51
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNativeUplinkPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNativeUplinkPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCNativeUplinkPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCNativeUplinkPortProfile

## SYNOPSIS
Removes a native uplink port profile.

## SYNTAX

```
Remove-SCNativeUplinkPortProfile [-VMMServer <ServerConnection>]
 [-NativeUplinkPortProfile] <NativeUplinkPortProfile> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCNativeUplinkPortProfile** cmdlet deletes a native uplink port profile.

## EXAMPLES

### Example 1: Remove a native uplink port profile
```
PS C:\> Get-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01" | Remove-SCNativeUplinkPortProfile
```

This command gets the native uplink port profile object named NativeUplinkPortProfile01 and uses the pipeline operator to pass the object to **Remove-SCNativeUplinkPortProfile**, which deletes the native uplink port profile.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -NativeUplinkPortProfile
Specifies a native uplink port profile object.

```yaml
Type: NativeUplinkPortProfile
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

## NOTES

## RELATED LINKS

[Get-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNativeUplinkPortProfile.md)

[New-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCNativeUplinkPortProfile.md)

[Set-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNativeUplinkPortProfile.md)

