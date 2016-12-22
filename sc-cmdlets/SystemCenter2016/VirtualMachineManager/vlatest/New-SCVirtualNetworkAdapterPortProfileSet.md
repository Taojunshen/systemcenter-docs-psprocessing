---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2DC20B9B-6A76-460A-8930-DA60259A577A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualNetworkAdapterPortProfileSet

## SYNOPSIS
Creates a virtual network adapter port profile set.

## SYNTAX

```
New-SCVirtualNetworkAdapterPortProfileSet [-IsDefaultPortProfileSet <Boolean>]
 -PortClassification <PortClassification>
 [-VirtualNetworkAdapterNativePortProfile <VirtualNetworkAdapterNativePortProfile>]
 [-VirtualNetworkAdapterExtensionPortProfiles <VirtualNetworkAdapterExtensionPortProfile[]>]
 [-VMMServer <ServerConnection>] [[-Name] <String>] [[-Description] <String>] -LogicalSwitch <LogicalSwitch>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualNetworkAdapterPortProfileSet** cmdlet creates a virtual network adapter port profile set.

To create the virtual network adapter port profile set, you must provide a port classification and logical switch.
To obtain a port classification object, use the **Get-SCPortClassification** cmdlet.
To obtain a logical switch object, use the **Get-SCLogicalSwitch** cmdlet.

## EXAMPLES

### Example 1: Create a virtual network adapter port profile set
```
PS C:\> $PortClass = Get-SCPortClassification -Name "PortClass01"
PS C:\> $LogSwitch = Get-SCLogicalSwitch -Name "LogicalSwitch01"
PS C:\> New-SCVirtualNetworkAdapterPortProfileSet -Name "VirtualNetworkAdapterPortProfSet01" -PortClassification $PortClass -LogicalSwitch $LogSwitch
```

The first command gets the port classification object named PortClass01 and stores the object in the $PortClass variable.

The second command gets the logical switch object named LogicalSwitch01 and stores the object in the $LogicalSwitch variable.

The last command creates a virtual network adapter port profile set with the name VirtualNetworkAdapterPortProfileSet01 using PortClass01 and LogicalSwitch01.

## PARAMETERS

### -Description
Specifies a description for the port profile set.

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

### -IsDefaultPortProfileSet
Indicates whether this is the default port profile set.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -LogicalSwitch
Specifies a logical switch object.

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
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### -PortClassification
Specifies the port classification of the switch to which the virtual network adapter connects.

```yaml
Type: PortClassification
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies a VMM server object.

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

### -VirtualNetworkAdapterExtensionPortProfiles
Specifies an array of virtual network adapter extension port profiles.

```yaml
Type: VirtualNetworkAdapterExtensionPortProfile[]
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

To obtain a virtual network adapter native port profile object, use the **Get-SCVirtualNetworkAdapterNativePortProfile** cmdlet.

```yaml
Type: VirtualNetworkAdapterNativePortProfile
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

[Get-SCPortClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPortClassification.md)

[Get-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterPortProfileSet.md)

[Remove-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapterPortProfileSet.md)

[Set-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterPortProfileSet.md)

