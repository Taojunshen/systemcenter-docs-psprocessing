---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2516C7CB-8BEF-451A-9B5D-2F51C1183D0E
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFibreChannelAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFibreChannelAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFibreChannelAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualFibreChannelAdapter

## SYNOPSIS
Modifies a Virtual Fibre Channel adapter.

## SYNTAX

### Default (Default)
```
Set-SCVirtualFibreChannelAdapter [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>]
 [-StorageFabricClassification <StorageFabricClassification>]
 [-VirtualFibreChannelAdapter] <VirtualFibreChannelAdapter> [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### DynamicAddress
```
Set-SCVirtualFibreChannelAdapter [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>]
 [-StorageFabricClassification <StorageFabricClassification>]
 [-VirtualFibreChannelAdapter] <VirtualFibreChannelAdapter> [-JobGroup <Guid>] [-DynamicWorldWideName]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### StaticAddress
```
Set-SCVirtualFibreChannelAdapter [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>]
 [-StorageFabricClassification <StorageFabricClassification>]
 [-VirtualFibreChannelAdapter] <VirtualFibreChannelAdapter> [-JobGroup <Guid>] [-StaticWorldWideName]
 [-PrimaryWorldWideNodeName <String>] [-PrimaryWorldWidePortName <String>]
 [-SecondaryWorldWideNodeName <String>] [-SecondaryWorldWidePortName <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualFibreChannelAdapter** cmdlet modifies a Virtual Fibre Channel adapter.

## EXAMPLES


## PARAMETERS

### -DynamicWorldWideName
Indicates that the cmdlet uses the dynamic world-wide name provided by Hyper-V.

```yaml
Type: SwitchParameter
Parameter Sets: DynamicAddress
Aliases: 

Required: True
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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -PrimaryWorldWideNodeName
Specifies the primary world-wide node name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: StaticAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryWorldWidePortName
Specifies the primary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: StaticAddress
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

### -SecondaryWorldWideNodeName
Specifies the secondary world-wide node name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: StaticAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryWorldWidePortName
Specifies the secondary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: StaticAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticWorldWideName
Indicates that the cmdlet uses the static world-wide name provided by the administrator.

```yaml
Type: SwitchParameter
Parameter Sets: StaticAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageFabricClassification
Specifies a classification for storage Fibre Channel fabric.

```yaml
Type: StorageFabricClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualFibreChannelAdapter
Specifies a virtual machine Virtual Fibre Channel adapter object.

```yaml
Type: VirtualFibreChannelAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualFibreChannelSAN
Specifies a host Fibre Channel virtual SAN object.

```yaml
Type: HostFibreChannelVirtualSAN
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualFibreChannelAdapter
This cmdlet returns a **VirtualFibreChannelAdapter** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualFibreChannelAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualFibreChannelAdapter.md)

[New-SCVirtualFibreChannelAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualFibreChannelAdapter.md)

[Remove-SCVirtualFibreChannelAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualFibreChannelAdapter.md)

