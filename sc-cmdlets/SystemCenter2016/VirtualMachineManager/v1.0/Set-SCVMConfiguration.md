---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierConfiguration.md
schema: 2.0.0
ms.assetid: 67E205D6-ABEE-4CBE-8886-966410E20CCF
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMConfiguration

## SYNOPSIS
Modifies the virtual machine configuration for a computer tier.

## SYNTAX

### Update (Default)
```
Set-SCVMConfiguration [-VMLocation <String>] [-PinVMLocation <Boolean>] [-ComputerName <String>]
 [-PinVMHost <Boolean>] [-CapabilityProfile <CapabilityProfile>] [-VMMServer <ServerConnection>]
 [-VMConfiguration] <BaseVMConfiguration> [-Description <String>] [-Tag <String>] [-CostCenter <String>]
 [-Name <String>] [-NoConnectedHost] [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMHost
```
Set-SCVMConfiguration [-VMLocation <String>] [-PinVMLocation <Boolean>] [-ComputerName <String>] -VMHost <Host>
 [-PinVMHost <Boolean>] [-CapabilityProfile <CapabilityProfile>] [-VMConfiguration] <BaseVMConfiguration>
 [-Description <String>] [-Tag <String>] [-CostCenter <String>] [-Name <String>] [-NoConnectedHost]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### VMHostGroup
```
Set-SCVMConfiguration [-VMLocation <String>] [-PinVMLocation <Boolean>] [-ComputerName <String>]
 [-PinVMHost <Boolean>] [-VMHostGroup <HostGroup>] [-CapabilityProfile <CapabilityProfile>]
 [-VMMServer <ServerConnection>] [-VMConfiguration] <BaseVMConfiguration> [-Description <String>]
 [-Tag <String>] [-CostCenter <String>] [-Name <String>] [-NoConnectedHost]
 [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### Cloud
```
Set-SCVMConfiguration [-VMLocation <String>] [-PinVMLocation <Boolean>] [-ComputerName <String>]
 [-PinVMHost <Boolean>] -Cloud <Cloud> [-CapabilityProfile <CapabilityProfile>]
 [-VMConfiguration] <BaseVMConfiguration> [-Description <String>] [-Tag <String>] [-CostCenter <String>]
 [-Name <String>] [-NoConnectedHost] [-AvailabilitySetNames <System.Collections.Generic.List`1[System.String]>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMConfiguration** cmdlet modifies the virtual machine configuration for a computer tier.
The virtual machine configuration describes how the virtual machine will be configured when the service is deployed.

## EXAMPLES

### Example 1: Update the virtual machine configuration for a machine tier prior to deploying the service
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> Set-SCVMConfiguration -VMConfiguration $VMConfig[0] -Description "This is the updated virtual machine configuration"
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the variable in the $VMConfig variable.

The last command sets the description property of the first virtual machine configuration object stored in $VMConfig, and displays the properties of the virtual machine configuration to the user.

### Example 2: Configure the virtual machine configuration object for a machine tier to pin the host for a virtual machine
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01" 
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig 
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> Set-SCVMConfiguration -VMConfiguration $VMConfig[0] -PinVMHost $True
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration object for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration objects for the computer tier configuration stored in $TierConfig and stores the objects in the $VMConfig variable.

The last command sets the PinVMHost propety to $True for the first virtual machine configuration object stored in $VMConfig.
Therefore, when the service is deployed, the host for the virtual machine created with this configuration will not be changed.

### Example 3: Configure the virtual machine configuration object for a service in a private cloud
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig 
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $Cloud = Get-SCCloud -Name "Production"
PS C:\> Set-SCVMConfiguration -VMConfiguration $VMConfig[1] -Cloud $Cloud -Description "This is the new virtual machine configuration"
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration objects for the computer tier configuration stored in $TierConfig and stores the objects in the $VMConfig variable.

The fourth command gets the private cloud object named Production and stores the object in the $Cloud variable.

The last command updates the description for the second virtual machine configuration object stored in $VMConfig for the private cloud stored in $Cloud.

## PARAMETERS

### -AvailabilitySetNames
Specifies a list of availability set names.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that Virtual Machine Manager (VMM) can uniquely identify on your network.
Valid formats are: 

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### -CostCenter
Specifies the cost center for a virtual machine so that you can collect data about the allocation of virtual machines (or resources allocated to virtual machines) to make use of in your billing system.

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

### -Description
Specifies a description for the configuration.

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

### -Name
Specifies the name of a VMM object.

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

### -NoConnectedHost
Removes the host from a virtual machine configuration.

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

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the Get-SCUserRole cmdlet.

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

### -PinVMHost
Indicates whether the virtual machine host chosen by the user is retained during service deployment configuration.

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

### -PinVMLocation
Indicates whether the virtual machine location chosen by the user is retained during service deployment configuration.

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

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

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

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: BaseVMConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: VMHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: VMHostGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMLocation
Specifies the path to a virtual machine.

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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: Update, VMHostGroup
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

### VMConfiguration
This cmdlet returns a **VMConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md)

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMConfiguration.md)

[New-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCVMConfiguration.md)

[Remove-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMConfiguration.md)

[Update-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Update-SCVMConfiguration.md)

