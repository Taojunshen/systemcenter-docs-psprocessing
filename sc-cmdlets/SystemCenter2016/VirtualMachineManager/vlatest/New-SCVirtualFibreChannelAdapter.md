---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualFibreChannelAdapter.md
schema: 2.0.0
ms.assetid: 3A4C80CB-FE9A-40AA-97F2-06FA17D95532
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualFibreChannelAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualFibreChannelAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualFibreChannelAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVirtualFibreChannelAdapter

## SYNOPSIS
Creates a Virtual Fibre Channel adapter in a hardware profile, virtual machine template, or virtual machine instance.

## SYNTAX

### VMDynamicAddress (Default)
```
New-SCVirtualFibreChannelAdapter -VM <VM> [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>]
 [-DynamicWorldWideName] [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### JobGroupDynamic
```
New-SCVirtualFibreChannelAdapter [-VMMServer <ServerConnection>] -JobGroup <Guid>
 [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>] [-DynamicWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### JobGroupStatic
```
New-SCVirtualFibreChannelAdapter [-VMMServer <ServerConnection>] -JobGroup <Guid>
 [-PrimaryWorldWideNodeName <String>] [-PrimaryWorldWidePortName <String>]
 [-SecondaryWorldWideNodeName <String>] [-SecondaryWorldWidePortName <String>]
 [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>] [-StaticWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMStaticAddress
```
New-SCVirtualFibreChannelAdapter -VM <VM> -PrimaryWorldWideNodeName <String> -PrimaryWorldWidePortName <String>
 -SecondaryWorldWideNodeName <String> -SecondaryWorldWidePortName <String>
 [-VirtualFibreChannelSAN <HostFibreChannelVirtualSAN>] [-StaticWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### TemplateStaticAddress
```
New-SCVirtualFibreChannelAdapter -VMTemplate <Template> [-StaticWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### TemplateDynamicAddress
```
New-SCVirtualFibreChannelAdapter -VMTemplate <Template> [-DynamicWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfileStaticAddress
```
New-SCVirtualFibreChannelAdapter -HardwareProfile <HardwareProfile> [-StaticWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### HardwareProfileDynamicAddress
```
New-SCVirtualFibreChannelAdapter -HardwareProfile <HardwareProfile> [-DynamicWorldWideName]
 [-StorageFabricClassification <StorageFabricClassification>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVirtualFibreChannelAdapter** cmdlet creates a Virtual Fibre Channel adapter in a hardware profile, virtual machine template, or virtual machine instance.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DynamicWorldWideName
Indicates that the cmdlet uses the dynamic world-wide name provided by Hyper-V.

```yaml
Type: SwitchParameter
Parameter Sets: VMDynamicAddress, JobGroupDynamic, TemplateDynamicAddress, HardwareProfileDynamicAddress
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfileStaticAddress, HardwareProfileDynamicAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: JobGroupDynamic, JobGroupStatic
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
To obtain a user role, use the Get-SCUserRole cmdlet.
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
Parameter Sets: JobGroupStatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VMStaticAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryWorldWidePortName
Specifies the primary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: JobGroupStatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VMStaticAddress
Aliases: 

Required: True
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
Specifies the secondary world-wide node name for a virtual machine virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: JobGroupStatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VMStaticAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecondaryWorldWidePortName
Specifies the secondary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

```yaml
Type: String
Parameter Sets: JobGroupStatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: VMStaticAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StaticWorldWideName
Indicates that the cmdlet uses the static world-wide name provided by the administrator.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroupStatic, VMStaticAddress, TemplateStaticAddress, HardwareProfileStaticAddress
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

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VMDynamicAddress, VMStaticAddress
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

```yaml
Type: ServerConnection
Parameter Sets: JobGroupDynamic, JobGroupStatic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: TemplateStaticAddress, TemplateDynamicAddress
Aliases: Template

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualFibreChannelSAN
Specifies a host Fibre Channel virtual SAN object.

```yaml
Type: HostFibreChannelVirtualSAN
Parameter Sets: VMDynamicAddress, JobGroupDynamic, JobGroupStatic, VMStaticAddress
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

[Remove-SCVirtualFibreChannelAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualFibreChannelAdapter.md)

[Set-SCVirtualFibreChannelAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualFibreChannelAdapter.md)

