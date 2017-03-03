---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7EA53818-EEC1-4E26-99D0-CCD4ED396DFC
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUplinkPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUplinkPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUplinkPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCUplinkPortProfileSet

## SYNOPSIS
Modifies an uplink port profile set.

## SYNTAX

```
Set-SCUplinkPortProfileSet [-NativeUplinkPortProfile <NativeUplinkPortProfile>]
 [-AddExtensionUplinkPortProfiles <ExtensionUplinkPortProfile[]>]
 [-RemoveExtensionUplinkPortProfiles <ExtensionUplinkPortProfile[]>] [-VMMServer <ServerConnection>]
 [-UplinkPortProfileSet] <UplinkPortProfileSet> [-Name <String>] [[-Description] <String>]
 [-LogicalSwitch <LogicalSwitch>] [-RemoveNativeUplinkPortProfile] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCUplinkPortProfileSet** cmdlet modifies the properties of an uplink port profile set.

## EXAMPLES

### Example 1: Remove a native uplink port profile from an uplink port profile set
```
PS C:\> Get-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01" | Set-SCUplinkPortProfileSet -RemoveNativeUplinkPortProfile
```

This command gets the uplink port profile set object named UplinkPortProfileSet01, and then passes it to the current cmdlet.
**Set-SCUplinkPortProfileSet** removes the native uplink port profile from the uplink port profile set.

## PARAMETERS

### -AddExtensionUplinkPortProfiles
Specifies an array of uplink port profile objects that this cmdlet adds.

```yaml
Type: ExtensionUplinkPortProfile[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description for the uplink port profile set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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

### -LogicalSwitch
Specifies a logical switch that this cmdlet includes in the uplink port profile set.
To obtain a logical switch object, use the **Get-SCLogicalSwitch** cmdlet.

```yaml
Type: LogicalSwitch
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM in which this cmdlet modifies an uplink port profile set.

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
Specifies a native uplink port profile that this cmdlet assigns to the new uplink port profile set.

```yaml
Type: NativeUplinkPortProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

### -RemoveExtensionUplinkPortProfiles
Specifies an array of extension uplink port profiles that this cmdlet removes from the port profile set.

```yaml
Type: ExtensionUplinkPortProfile[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveNativeUplinkPortProfile
Indicates that this cmdlet removes the native uplink port profile.

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

### -UplinkPortProfileSet
Specifies the uplink port profile set that this cmdlet modifies.
To obtain an uplink port profile set object, use the **Get-SCUplinkPortProfileSet** cmdlet.

```yaml
Type: UplinkPortProfileSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server on which this cmdlet modifies an uplink port profile set.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUplinkPortProfileSet.md)

[New-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCUplinkPortProfileSet.md)

[Remove-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUplinkPortProfileSet.md)

