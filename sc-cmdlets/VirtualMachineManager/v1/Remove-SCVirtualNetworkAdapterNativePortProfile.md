---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualNetworkAdapterNativePortProfile.md
schema: 2.0.0
ms.assetid: 17C23B28-9826-4E25-ABB1-FB58E54DA798
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterNativePortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterNativePortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterNativePortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualNetworkAdapterNativePortProfile

## SYNOPSIS
Removes a virtual network adapter native port profile.

## SYNTAX

```
Remove-SCVirtualNetworkAdapterNativePortProfile [-VMMServer <ServerConnection>]
 [-VirtualNetworkAdapterNativePortProfile] <VirtualNetworkAdapterNativePortProfile> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualNetworkAdapterNativePortProfile** cmdlet deletes a virtual network adapter native port profile.

## EXAMPLES

### Example 1: Remove a virtual network adapter native port profile
```
PS C:\>Get-SCVirtualNetworkAdapterNativePortProfile -Name "VirtualNetworkAdapterNativePortProf01" | Remove-SCVirtualNetworkAdapterNativePortProfile
```

This command gets the virtual network adapter native port profile object named VirtualNetworkAdapterNativePortProf01 and passes the object to **Remove-SCVirtualNetworkAdapterNativePortProfile**, which deletes the profile object.

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

### -VirtualNetworkAdapterNativePortProfile
Specifies a virtual network adapter native port profile object.

To obtain a virtual network adapter native port profile object, use the Get-SCVirtualNetworkAdapterNativePortProfile cmdlet.

```yaml
Type: VirtualNetworkAdapterNativePortProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-SCVirtualNetworkAdapterNativePortProfile](xref:VirtualMachineManager/v1/Get-SCVirtualNetworkAdapterNativePortProfile.md)

[New-SCVirtualNetworkAdapterNativePortProfile](xref:VirtualMachineManager/v1/New-SCVirtualNetworkAdapterNativePortProfile.md)

[Set-SCVirtualNetworkAdapterNativePortProfile](xref:VirtualMachineManager/v1/Set-SCVirtualNetworkAdapterNativePortProfile.md)

