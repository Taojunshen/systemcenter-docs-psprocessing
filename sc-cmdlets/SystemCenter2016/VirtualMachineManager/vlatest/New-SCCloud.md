---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 275C33C6-419B-418D-AE58-349A6D998330
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCloud.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCloud.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCCloud.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCCloud

## SYNOPSIS
Creates a private cloud.

## SYNTAX

### VMHostGroup (Default)
```
New-SCCloud [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] -VMHostGroup <HostGroup[]>
 [-DisasterRecoverySupported <Boolean>] [-ShieldedVMSupportPolicy <ShieldedVMSupportPolicyEnum>]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VMwareResourcePool
```
New-SCCloud [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 -VMwareResourcePool <VmwResourcePool> [-DisasterRecoverySupported <Boolean>]
 [-ShieldedVMSupportPolicy <ShieldedVMSupportPolicyEnum>] [-JobGroup <Guid>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCCloud** cmdlet creates a private cloud in Virtual Machine Manager (VMM).
A private cloud is a cloud that is provisioned and managed on-premise by an organization.
The private cloud is deployed using an organization's own hardware to leverage the advantages of the private cloud model.
Through VMM, an organization can manage the private cloud definition, access to the private cloud, and the underlying physical resources.

You can create a private cloud from the following resources: 

- Host groups that contain resources from Hyper-V hosts, Citrix XenServer hosts, and VMware ESX hosts
- A VMware resource pool

For more information about private clouds, see ["Creating a Private Cloud Overview"](http://go.microsoft.com/fwlink/?LinkID=212407) in the TechNet library at [http://go.microsoft.com/fwlink/?LinkID=212407](http://go.microsoft.com/fwlink/?LinkID=212407). 
For information about private cloud capacity, type: `Get-Help Set-SCCloudCapacity -Detailed`.

## EXAMPLES

### Example 1: Create a private cloud from a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup01"
PS C:\> New-SCCloud -Name "Cloud01" -VMHostGroup $HostGroup
```

The first command gets the host group named HostGroup01 and stores it in the $HostGroup variable.

The second command creates a private cloud named Cloud01 from the host group stored in the $HostGroup variable.

### Example 2: Create a private cloud using a job group
```
PS C:\> $Guid = [System.Guid]::NewGuid()
PS C:\> Set-SCCloud -JobGroup $Guid
PS C:\> $HostGroup = Get-SCVMHostGroup -Name "HostGroup02"
PS C:\> New-SCCloud -JobGroup $Guid -Name "Cloud02" -VMHostGroup $HostGroup -Description "This is a cloud for HostGorup02"
```

The first command creates a new GUID and stores it in the $Guid variable.

The second command creates a job group using the GUID stored in $Guid.

The third command gets the host group object named HostGroup02 and stores the object in the $HostGroup variable.

The last command creates a private cloud named Cloud02, using the job group created in the second command and HostGroup02 for its resources.

### Example 3: Create a private cloud from multiple host groups
```
PS C:\> $HostGroups = @()
PS C:\> $HostGroups += Get-SCVMHostGroup -Name "Seattle"
PS C:\> $HostGroups += Get-SCVMHostGroup -Name "New York"
PS C:\> New-SCCloud -VMHostGroup $HostGroups -Name "Cloud03" -Description "Cloud for the Seattle and New York host groups"
```

The first command creates an object array named $HostGroups.

The second and third commands populate the object array with the host groups named Seattle and New York.

The last command creates a private cloud named Cloud03 using the host groups stored in the $HostGroups array as its resources.

## PARAMETERS

### -Description
Specifies a description for the private cloud.

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

### -DisasterRecoverySupported
Indicates whether the Windows Azure Hyper-V Recovery Manager service is enabled.

If you enable this parameter, the cmdlet sends the following data over the internet to the service: cloud name, virtual machine names, logical network names, virtual machine host names, and the relevant properties for each object.
If sending this information conflicts with existing privacy requirements for workloads that are deployed to this cloud, then do not select this option.

After you pair this cloud to a recovery cloud in Windows Azure Hyper-V Recovery Manager, you cannot disable this option.

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

### -Name
Specifies the name of a VMM object.

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

### -ShieldedVMSupportPolicy
Indicates whether this cloud supports placing shielded virtual machines on it, so placement will provide ratings for the cloud.

```yaml
Type: ShieldedVMSupportPolicyEnum
Parameter Sets: (All)
Aliases: 
Accepted values: ShieldedVMNotSupported, ShieldedVMSupported

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup[]
Parameter Sets: VMHostGroup
Aliases: 

Required: True
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

### -VMwareResourcePool
Specifies a virtual machine to be assigned and deployed on a VMware ESX host or a private cloud to a specific VMware resource pool.

```yaml
Type: VmwResourcePool
Parameter Sets: VMwareResourcePool
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Cloud
This cmdlet returns a **Cloud** object.

## NOTES

## RELATED LINKS

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[Remove-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCloud.md)

[Set-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloud.md)

