---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8DECB130-E57E-42FE-9D44-2825C32FEB61
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDiskConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDiskConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualHardDiskConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualHardDiskConfiguration

## SYNOPSIS
Modifies the virtual hard disk configuration information contained within a virtual machine configuration.

## SYNTAX

```
Set-SCVirtualHardDiskConfiguration [-SourceDisk <StandaloneVirtualHardDisk>] [-PinSourceLocation <Boolean>]
 [-DestinationLocation <String>] [-PinDestinationLocation <Boolean>] [-FileName <String>]
 [-PinFileName <Boolean>] [-DeploymentOption <DeploymentOption>] [-StorageDisk <StorageDisk>]
 [-StorageClassification <StorageClassification>] [-StorageQoSPolicy <StorageQoSPolicy>]
 [-PinStorageDisk <Boolean>] [-ParentVirtualHardDiskPath <String>]
 [-ParentVirtualHardDiskDestinationPath <String>] [-FileInjectionSourceLocation <String>]
 [-FileInjectionDestinationLocation <String>] [-FileInjectionDestinationPartition <Int16>]
 -VHDConfiguration <VirtualHardDiskConfiguration> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualHardDiskConfiguration** cmdlet modifies the virtual hard disk configuration information that is contained within a virtual machine configuration.

## EXAMPLES

### Example 1: Set the properties of a virtual hard disk configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01" 
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $VHDConfig = Get-SCVirtualHardDiskConfiguration -VMConfiguration $VMConfig[0]
PS C:\> $VHD = Get-SCVirtualHardDisk -Name "Win2k8R2BaseDisk.vhd"
PS C:\> Set-SCVirtualHardDiskConfiguration -VHDConfiguration $VHDConfig -SourceDisk $VHD -PinSourceLocation $True
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration object stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The fourth command gets the virtual hard disk configuration for the first virtual machine configuration stored in $VMConfig and stores the object in the $VHDConfig variable.

The fifth command gets the virtual hard disk object named Win2k8R2BaseDisk.vhd from the library and stores the object in the $VHD variable.

The last command updates the PinSourceLocation property in the virtual hard disk configuration stored in $VHDConfig for the source virtual hard disk stored in $VHD to pin the value of the source virtual hard disk, thereby preventing it from being changed during placement.

## PARAMETERS

### -DeploymentOption
Specifies the deployment option for a virtual hard disk.
The acceptable values for this parameter are:

- None
- UseFastest
- UseTarget
- UseNetwork
- UseSAN
- UseDifferencing
- UseExistingVirtualDisk

```yaml
Type: DeploymentOption
Parameter Sets: (All)
Aliases: 
Accepted values: None, UseFastest, UseTarget, UseNetwork, UseSAN, UseDifferencing, UseExistingVirtualDisk

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationLocation
Specifies the destination path for or on a virtual hard disk.

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

### -FileInjectionDestinationLocation
Specifies the target folder path (relative path to the root of the partition) where the source file(s) are injected into the selected VHD before turning on the virtual machine for the first time.

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

### -FileInjectionDestinationPartition
Specifies the target partition of the selected VHD where the source files are injected before turning on the virtual machine for the first time.

```yaml
Type: Int16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileInjectionSourceLocation
Specifies the location (an URL) of the file(s) to inject into the virtual machine before turning on the virtual machine for the first time.

When a folder is specified, all files under that folder are injected into the specified destination location.

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

### -FileName
Specifies the file name to use when you rename a virtual hard disk file as you add it to a virtual machine.

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

### -ParentVirtualHardDiskDestinationPath
Specifies the destination path for parent virtual hard disk.

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

### -ParentVirtualHardDiskPath
Specifies the path to the parent virtual hard disk to be used when creating a differencing disk.

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

### -PinDestinationLocation
Indicates whether the destination location chosen by the user is retained during service deployment configuration.

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

### -PinFileName
Indicates whether the file name chosen by the user is retained during service deployment configuration.

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

### -PinSourceLocation
Indicates whether the source location chosen by the user is retained during service deployment configuration.

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

### -PinStorageDisk
Indicates whether the storage disk chosen by the user is retained during service deployment configuration.

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

### -SourceDisk
Specifies the source virtual hard disk.

```yaml
Type: StandaloneVirtualHardDisk
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageClassification
Specifies a storage classification object.

```yaml
Type: StorageClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageDisk
Specifies a disk on a Hyper-V or VMware ESX host that a virtual machine on that host can use instead of using a virtual hard disk.
This disk is referred to as a pass-through disk.
The corresponding VMware term is Raw Device Mapping (RDM).
The host disk is either a local hard disk or a logical unit on a Storage Area Network (SAN).
VMM lets the virtual machine bypass the host's file system and access the pass-through disk directly.
Hyper-V hosts support pass-through disks and conversion of a pass-through disk to a VHD.
VMware ESX hosts support pass-through disks, but not disk conversion.
Citrix XenServer hosts do not support pass-through disks.

```yaml
Type: StorageDisk
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageQoSPolicy
Specifies a **StorageQoSPolicy** object.

```yaml
Type: StorageQoSPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VHDConfiguration
Specifies a virtual hard disk configuration object.

```yaml
Type: VirtualHardDiskConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualHardDiskConfiguration
This cmdlet returns a **VirtualHardDiskConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceConfiguration.md)

[Get-SCVirtualHardDisk](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDisk.md)

[Get-SCVirtualHardDiskConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualHardDiskConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMConfiguration.md)

