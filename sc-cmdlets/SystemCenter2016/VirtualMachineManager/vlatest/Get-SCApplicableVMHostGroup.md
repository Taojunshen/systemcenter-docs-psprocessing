---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9856ECD9-37BD-463B-B4A1-A7B335B81CD1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicableVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicableVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicableVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCApplicableVMHostGroup

## SYNOPSIS
Gets an applicable host group.

## SYNTAX

### ByLogicalSwitch
```
Get-SCApplicableVMHostGroup [-VMMServer <ServerConnection>] -LogicalSwitch <LogicalSwitch> [<CommonParameters>]
```

### ByUplinkPortProfileSet
```
Get-SCApplicableVMHostGroup [-VMMServer <ServerConnection>] -UplinkPortProfileSet <UplinkPortProfileSet>
 [<CommonParameters>]
```

### ByNativeUplinkPortProfile
```
Get-SCApplicableVMHostGroup [-VMMServer <ServerConnection>] -NativeUplinkPortProfile <NativeUplinkPortProfile>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicableVMHostGroup** cmdlet gets the host group associated with a logical switch, a native uplink port profile, or an uplink port profile set.

## EXAMPLES

### Example 1: Get the applicable host group for a logical switch
```
PS C:\> $LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> Get-SCApplicableVMHostGroup -LogicalSwitch $LogSwitch
```

The first command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogSwitch variable.

The second command gets the applicable host group for the logical switch stored in $LogSwitch.

### Example 2: Get the applicable host group for an uplink port profile set
```
PS C:\> $UplinkPortProfSet = Get-SCUplinkPortProfileSet -Name "UplinkPortProfileSet01"
PS C:\> Get-SCApplicableVMHostGroup -UplinkPortProfileSet $UplinkPortProfSet
```

The first command gets the uplink port profile set object named UplinkPortProfileSet01 and stores the object in the $UplinkPortProfSet variable.

The second command gets the applicable host group for the uplink port profile set stored in $UplinkPortProfSet.

### Example 3: Get the applicable host group for a NativeUplinkPortProfile
```
PS C:\> $NativeUplinkPortProf = Get-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01"
PS C:\> Get-SCApplicableVMHostGroup -NativeUplinkPortProfile $NativeUplinkPortProf
```

The first command gets the native uplink port profile object named NativeUplinkPortProfile01 and stores the object in the $NativeUplinkPortProf variable.

The second command gets the applicable host group for the native uplink port profile stored in $NativeUplinkPortProf.

## PARAMETERS

### -LogicalSwitch
Specifies a logical switch object.

```yaml
Type: LogicalSwitch
Parameter Sets: ByLogicalSwitch
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NativeUplinkPortProfile
Specifies a native uplink port profile object.

```yaml
Type: NativeUplinkPortProfile
Parameter Sets: ByNativeUplinkPortProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UplinkPortProfileSet
Specifies an uplink port profile set object.

To obtain an uplink port profile set object, use the **Get-SCUplinkPortProfileSet** cmdlet.

```yaml
Type: UplinkPortProfileSet
Parameter Sets: ByUplinkPortProfileSet
Aliases: 

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCLogicalSwitch](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLogicalSwitch.md)

[Get-SCNativeUplinkPortProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNativeUplinkPortProfile.md)

[Get-SCUplinkPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUplinkPortProfileSet.md)

