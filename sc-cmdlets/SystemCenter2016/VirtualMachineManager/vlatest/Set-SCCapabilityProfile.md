---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DC57B72C-D1CF-41B7-BEC5-986BFAD4968B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCCapabilityProfile

## SYNOPSIS
Modifies the properties of a capability profile.

## SYNTAX

### FromName
```
Set-SCCapabilityProfile -CapabilityProfile <CapabilityProfile> -Name <String> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### FromValues
```
Set-SCCapabilityProfile -CapabilityProfile <CapabilityProfile> [-Description <String>]
 [-CPUCountInitial <Int32>] [-CPUCountMaximum <Int32>] [-CPUCountMinimum <Int32>]
 [-CPUCompatibilityModeValue <Boolean>] [-CPUCompatibilityModeValueCanChange <Boolean>]
 [-OSCompatibilityModeValue <Boolean>] [-OSCompatibilityModeValueCanChange <Boolean>]
 [-MemoryMBInitial <Int32>] [-MemoryMBMaximum <Int32>] [-MemoryMBMinimum <Int32>]
 [-DynamicMemoryValue <Boolean>] [-DynamicMemoryValueCanChange <Boolean>] [-StartupMemoryMBInitial <Int32>]
 [-StartupMemoryMBMaximum <Int32>] [-StartupMemoryMBMinimum <Int32>] [-MaximumMemoryMBInitial <Int32>]
 [-MaximumMemoryMBMaximum <Int32>] [-MaximumMemoryMBMinimum <Int32>]
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

## DESCRIPTION
The **Set-SCCapabilityProfile** cmdlet modifies the properties of a capability profile object.

For information about creating a capability profile, type `Get-Help New-SCCapabilityProfile -Detailed`.

## EXAMPLES

### Example 1: Modify the default virtual hard disk settings of a capability profile
```
PS C:\> $CapabilityProfile = Get-SCCapabilityProfile -Name "CapabilityProf01"
PS C:\> Set-SCCapabilityProfile -CapabilityProfile $CapabilityProfile -VirtualHardDiskCountMinimum 1 -VirtualHardDiskCountMaximum 8 -VirtualHardDiskSizeMBMaximum 256000
```

The first command gets the capability profile object named CapabilityProf01 and stores the object in the $CapabilityProfile variable.

The second command sets the virtual hard disk minimum to 1, the virtual hard disk maximum to 8, and the maximum virtual hard disk size to 25600 MB (250 GB) for the capability profile stored in $CapabilityProfile.

## PARAMETERS

### -CPUCompatibilityModeValue
Indicates whether processor compatibility mode is enabled.
When set to $True, Virtual Machine Manager (VMM) limits the processor features that a virtual machine can use in order to improve compatibility with a different processor version.

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
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
States a description for the specified object.

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
Parameter Sets: FromName
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

## NOTES
* Requires a VMM capability profile object, which can be retrieved by using the **Get-SCCapabilityProfile** cmdlet.

## RELATED LINKS

[Get-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md)

[New-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md)

[Remove-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCapabilityProfile.md)

[Test-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md)

