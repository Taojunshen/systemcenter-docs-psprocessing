---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8B53F0D2-1BF8-4507-B93C-129D8EB1FDCA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCCapabilityProfile

## SYNOPSIS
Creates a capability profile.

## SYNTAX

### FromValues
```
New-SCCapabilityProfile -Name <String> -FabricCapabilityType <FabricCapabilityType>
 [-VMMServer <ServerConnection>] [-Description <String>] [-CPUCountInitial <Int32>] [-CPUCountMaximum <Int32>]
 [-CPUCountMinimum <Int32>] [-CPUCompatibilityModeValue <Boolean>]
 [-CPUCompatibilityModeValueCanChange <Boolean>] [-OSCompatibilityModeValue <Boolean>]
 [-OSCompatibilityModeValueCanChange <Boolean>] [-MemoryMBInitial <Int32>] [-MemoryMBMaximum <Int32>]
 [-MemoryMBMinimum <Int32>] [-DynamicMemoryValue <Boolean>] [-DynamicMemoryValueCanChange <Boolean>]
 [-StartupMemoryMBInitial <Int32>] [-StartupMemoryMBMaximum <Int32>] [-StartupMemoryMBMinimum <Int32>]
 [-MaximumMemoryMBInitial <Int32>] [-MaximumMemoryMBMaximum <Int32>] [-MaximumMemoryMBMinimum <Int32>]
 [-TargetMemoryBufferPercentInitial <Int32>] [-TargetMemoryBufferPercentMaximum <Int32>]
 [-TargetMemoryBufferPercentMinimum <Int32>] [-VirtualDVDDriveCountInitial <Int32>]
 [-VirtualDVDDriveCountMaximum <Int32>] [-VirtualDVDDriveCountMinimum <Int32>]
 [-SharedDVDImageFileValue <Boolean>] [-SharedDVDImageFileValueCanChange <Boolean>]
 [-VirtualHardDiskCountInitial <Int32>] [-VirtualHardDiskCountMaximum <Int32>]
 [-VirtualHardDiskCountMinimum <Int32>] [-DifferencingVirtualHardDiskValue <Boolean>]
 [-DifferencingVirtualHardDiskValueCanChange <Boolean>] [-DynamicVirtualHardDiskValue <Boolean>]
 [-DynamicVirtualHardDiskValueCanChange <Boolean>] [-FixedVirtualHardDiskValue <Boolean>]
 [-FixedVirtualHardDiskValueCanChange <Boolean>] [-VirtualHardDiskSizeMBInitial <Int32>]
 [-VirtualHardDiskSizeMBMaximum <Int32>] [-VirtualHardDiskSizeMBMinimum <Int32>]
 [-NewDiskStorageClassificationValue <Guid>] [-ExistDiskStorageClassificationValue <Guid>]
 [-VirtualNetworkAdapterCountInitial <Int32>] [-VirtualNetworkAdapterCountMaximum <Int32>]
 [-VirtualNetworkAdapterCountMinimum <Int32>] [-LogicalNetworkValue <Guid>]
 [-NetworkOptimizationValue <Boolean>] [-NetworkOptimizationValueCanChange <Boolean>]
 [-VMHighlyAvailableValue <Boolean>] [-VMHighlyAvailableValueCanChange <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### FromExisting
```
New-SCCapabilityProfile -Name <String> -CapabilityProfile <CapabilityProfile> [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCCapabilityProfile** cmdlet creates a capability profile object in Virtual Machine Manager (VMM).
A capability profile is used to specify the capabilities of a virtual machine on a supported hypervisor when the virtual machine is deployed to a private cloud.

## EXAMPLES

### Example 1: Create a capability profile that is compatible with Hyper-V hosts
```
PS C:\> $CapabilityProfile = New-SCCapabilityProfile -Name "CapabilityProf01" -FabricCapabilityType "HyperV"
PS C:\> $CapabilityProfile
```

The first command creates a capability profile object named CapabilityProf01 that is compatible with Hyper-V hosts and stores the object in the $CapabilityProfile variable.

The second command displays information about the capability profile stored in $CapabilityProfile to the user.

## PARAMETERS

### -CPUCompatibilityModeValue
Indicates whether processor compatibility mode is enabled.
When set to $True, VMM limits the processor features that a virtual machine can use in order to improve compatibility with a different processor version.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUCompatibilityModeValueCanChange
Indicates whether the value for CPU compatibility mode can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUCountInitial
Specifies the initial number of processors that a virtual machine will have when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUCountMaximum
Specifies the maximum number of processors that a virtual machine deployed in a private cloud can have.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CPUCountMinimum
Specifies the minimum number of processors that a virtual machine deployed in a private cloud can have.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CapabilityProfile
Specifies a capability profile object.

```yaml
Type: CapabilityProfile
Parameter Sets: FromExisting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the capability profile.

```yaml
Type: String
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DifferencingVirtualHardDiskValue
Indicates whether differencing disks are allowed.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DifferencingVirtualHardDiskValueCanChange
Indicates whether the value for differencing disks can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicMemoryValue
Indicates whether dynamic memory is enabled.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicMemoryValueCanChange
Indicates whether the value for dynamic memory can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicVirtualHardDiskValue
Indicates whether dynamic virtual hard disks are allowed.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DynamicVirtualHardDiskValueCanChange
Indicates whether the value for dynamic virtual hard disks can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExistDiskStorageClassificationValue
Specifies a GUID.

```yaml
Type: Guid
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FabricCapabilityType
Specifies a fabric capability type.
Fabric capability indicates the capabilities of the virtualization platform on which you will be deploying a virtual machine.
VMM ensures that the settings in a capability profile are compatible with the selected fabric capability.
The acceptable values for this parameter are:

- HyperV
- ESX
-  Xen

```yaml
Type: FabricCapabilityType
Parameter Sets: FromValues
Aliases: 
Accepted values: HyperV, ESX

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FixedVirtualHardDiskValue
Indicates whether fixed virtual hard disks are allowed.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FixedVirtualHardDiskValueCanChange
Indicates whether the value for fixed virtual hard disks can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
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

### -LogicalNetworkValue
Specifies a GUID.

```yaml
Type: Guid
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumMemoryMBInitial
Specifies the initial maximum amount of memory, in megabytes (MB), allocated to a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumMemoryMBMaximum
Specifies the highest amount of maximum memory, in megabytes (MB), that can be allocated to a virtual machine.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumMemoryMBMinimum
Specifies the lowest amount of maximum memory, in megabytes (MB), that can be allocated to a virtual machine.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMBInitial
Specifies the initial amount of memory, in megabytes (MB), allocated to a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMBMaximum
Specifies the maximum amount of memory, in megabytes (MB), that can be allocated to a virtual machine.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MemoryMBMinimum
Specifies the minimum amount of memory, in megabytes (MB), that can be allocated to a virtual machine.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkOptimizationValue
Indicates whether network optimization is enabled.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkOptimizationValueCanChange
Indicates whether the value for network optimization can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDiskStorageClassificationValue
Specifies a GUID.

```yaml
Type: Guid
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSCompatibilityModeValue
Indicates whether operating system compatibility mode is enabled.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSCompatibilityModeValueCanChange
Indicates whether the value for operating system compatibility can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
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

### -SharedDVDImageFileValue
Indicates whether shared DVD image mode is enabled.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SharedDVDImageFileValueCanChange
Indicates whether the value for shared DVD image mode can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupMemoryMBInitial
Specifies the initial amount of memory, in megabytes (MB), that is allocated to a virtual machine upon startup.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupMemoryMBMaximum
Specifies the maximum amount of memory, in megabytes (MB), that is allocated to a virtual machine upon startup.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartupMemoryMBMinimum
Specifies the minimum amount of memory, in megabytes (MB), that is allocated to a virtual machine upon startup.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetMemoryBufferPercentInitial
Specifies the initial percentage of memory above a virtual machine's current memory allocation that the host should try to reserve as a buffer.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetMemoryBufferPercentMaximum
Specifies the maximum percentage of memory above a virtual machine's current memory allocation that the host should try to reserve as a buffer.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetMemoryBufferPercentMinimum
Specifies the minimum percentage of memory above a virtual machine's current memory allocation that the host should try to reserve as a buffer.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHighlyAvailableValue
Indicates whether a deployed virtual machine will be highly available.

```yaml
Type: Boolean
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHighlyAvailableValueCanChange
Indicates whether the value indicating the high availability status of a virtual machine can be updated.

```yaml
Type: Boolean
Parameter Sets: FromValues
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

### -VirtualDVDDriveCountInitial
Specifies the initial number of DVD drives attached to a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDVDDriveCountMaximum
Specifies the maximum number of DVD drives that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualDVDDriveCountMinimum
Specifies the minimum number of DVD drives that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskCountInitial
Specifies the initial number of virtual hard disks attached to a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskCountMaximum
Specifies the maximum number of virtual hard disks that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskCountMinimum
Specifies the minimum number of virtual hard disks that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskSizeMBInitial
Specifies the initial hard disk size, in megabytes (MB), for a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskSizeMBMaximum
Specifies the maximum virtual hard disk size, in megabytes (MB), allowed for a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualHardDiskSizeMBMinimum
Specifies the minimum virtual hard disk size, in megabytes (MB), allowed for a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapterCountInitial
Specifies the initial number of virtual network adapters attached to a virtual machine when deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapterCountMaximum
Specifies the maximum number of virtual network adapters that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkAdapterCountMinimum
Specifies the minimum number of virtual network adapters that can be attached to a virtual machine deployed in a private cloud.

```yaml
Type: Int32
Parameter Sets: FromValues
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

### CloudCapabilityProfile
This cmdlet returns a **CloudCapabilityProfile** object.

## NOTES

## RELATED LINKS

[Get-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md)

[Remove-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCapabilityProfile.md)

[Set-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md)

[Test-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md)

