---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalSwitch.md
schema: 2.0.0
ms.assetid: 36F4E3EE-0986-4961-9DE2-095DC6D594F9
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCUplinkPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCUplinkPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCUplinkPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCUplinkPortProfileSet

## SYNOPSIS
Creates an uplink port profile set.

## SYNTAX

```
New-SCUplinkPortProfileSet -LogicalSwitch <LogicalSwitch> [-NativeUplinkPortProfile <NativeUplinkPortProfile>]
 [-ExtensionUplinkPortProfiles <ExtensionUplinkPortProfile[]>] [-VMMServer <ServerConnection>] [-Name] <String>
 [[-Description] <String>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCUplinkPortProfileSet** cmdlet creates an uplink port profile set.

You must provide a logical switch when you create an uplink port profile set.
To obtain a logical switch object, use the Get-SCLogicalSwitch cmdlet.

## EXAMPLES

### Example 1: Create an uplink port profile set
```
PS C:\>$LogicalSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> $NativeUplinkPortProfile = Get-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01"
PS C:\> New-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01" -LogicalSwitch $LogicalSwitch -NativeUplinkPortProfile $NativeUplinkPortProfile
```

The first command gets the logical switch named LogicalSwitch01, and then stores that object in the $LogicalSwitch variable.

The second command gets the native uplink port profile named NativeUplinkPortProfile01, and stores that object in the $NativeUplinkPortProfile variable.

The last command creates an uplink port profile set named UplinkPortProfileSet01 by using LogicalSwitch01 and NativeUplinkPortProfile01.

## PARAMETERS

### -Description
Specifies a description for the profile set.

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

### -ExtensionUplinkPortProfiles
Specifies an array of extension uplink port profiles.
To obtain an extension uplink port profile, use the Get-SCExtensionUplinkPortProfile cmdlet.

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
To obtain a logical switch object, use the Get-SCLogicalSwitch cmdlet.

```yaml
Type: LogicalSwitch
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object in which this cmdlet creates an uplink port profile set.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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
Specifies a VMM server on which this cmdlet creates an uplink port profile set.

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

[Get-SCLogicalSwitch](xref:VirtualMachineManager/v1/Get-SCLogicalSwitch.md)

[Get-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md)

[Get-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Get-SCUplinkPortProfileSet.md)

[Remove-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Remove-SCUplinkPortProfileSet.md)

[Set-SCUplinkPortProfileSet](xref:VirtualMachineManager/v1/Set-SCUplinkPortProfileSet.md)

