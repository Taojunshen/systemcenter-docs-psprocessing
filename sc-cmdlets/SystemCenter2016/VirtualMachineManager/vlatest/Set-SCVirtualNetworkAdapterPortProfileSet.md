---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9E8131B9-F71B-427E-9D35-0072366948FF
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapterPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVirtualNetworkAdapterPortProfileSet

## SYNOPSIS
Sets the properties of a virtual network adapter port profile set.

## SYNTAX

```
Set-SCVirtualNetworkAdapterPortProfileSet [-IsDefaultPortProfileSet <Boolean>] [-LogicalSwitch <LogicalSwitch>]
 [-PortClassification <PortClassification>]
 [-VirtualNetworkAdapterNativePortProfile <VirtualNetworkAdapterNativePortProfile>]
 [-AddVirtualNetworkAdapterExtensionPortProfiles <VirtualNetworkAdapterExtensionPortProfile[]>]
 [-RemoveVirtualNetworkAdapterExtensionPortProfiles <VirtualNetworkAdapterExtensionPortProfile[]>]
 [-VMMServer <ServerConnection>] [-VirtualNetworkAdapterPortProfileSet] <VirtualNetworkAdapterPortProfileSet>
 [-Name <String>] [[-Description] <String>] [-RemoveVirtualNetworkAdapterNativePortProfile] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualNetworkAdapterPortProfileSet** cmdlet updates the properties of a virtual network adapter port profile set object.

## EXAMPLES

### Example 1: Remove a virtual network adapter native port profile from a virtual network adapter port profile set
```
PS C:\> Get-SCVirtualNetworkAdapterPortProfileSet -Name "VirtualNetworkAdapterPortProfSet01" | Set-SCVirtualNetworkAdapterPortProfileSet -RemoveVirtualNetworkAdapterNativePortProfile
```

This command gets the virtual network adapter port profile set object named VirtualNetworkAdapterPortProfSet01 and uses the pipeline operator to pass the object to **Set-SCVirtualNetworkAdapterPortProfileSet**, which removes the virtual network adapter native port profile from the virtual network adapter port profile set object.

## PARAMETERS

### -AddVirtualNetworkAdapterExtensionPortProfiles
Specifies an array of virtual network adapter extension port profiles that this cmdlet adds.

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

Required: False
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

### -PortClassification
Specifies the port classification of the switch to which the virtual network adapter connects.

```yaml
Type: PortClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RemoveVirtualNetworkAdapterExtensionPortProfiles
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

### -RemoveVirtualNetworkAdapterNativePortProfile
Indicates that this cmdlet removes the specified virtual network adapter native port profile.

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

### -VirtualNetworkAdapterNativePortProfile
Specifies a virtual network adapater native port profile object.

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

### -VirtualNetworkAdapterPortProfileSet
Specifies a virtual network adapter port profile set object.

To obtain a virtual network adapter port profile set object, use the Get-SCVirtualNetworkAdapterPortProfileSetcmdlet.

```yaml
Type: VirtualNetworkAdapterPortProfileSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapterPortProfileSet.md)

[New-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapterPortProfileSet.md)

[Remove-SCVirtualNetworkAdapterPortProfileSet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapterPortProfileSet.md)

