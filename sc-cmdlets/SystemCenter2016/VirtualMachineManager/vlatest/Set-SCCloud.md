---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 205839B4-739E-42AB-A4D7-3D2D1B769564
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloud.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloud.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloud.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCCloud

## SYNOPSIS
Changes the properties of a private cloud in VMM.

## SYNTAX

```
Set-SCCloud
 [-RemoveCapabilityProfile <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.CapabilityProfile]>]
 [-AddCapabilityProfile <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.CapabilityProfile]>]
 [-AddVMHostGroup <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.HostGroup]>]
 [-RemoveVMHostGroup <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.HostGroup]>]
 [-AddCloudResource <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ClientObject]>]
 [-RemoveCloudResource <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ClientObject]>]
 [-Name <String>] [-Description <String>]
 [-AddReadOnlyLibraryShare <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.LibraryShare]>]
 [-RemoveReadOnlyLibraryShare <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.LibraryShare]>]
 [-ReadWriteLibraryPath <String>] [-DisasterRecoverySupported <Boolean>]
 [-ShieldedVMSupportPolicy <ShieldedVMSupportPolicyEnum>] [-VMMServer <ServerConnection>] [[-Cloud] <Cloud>]
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCCloud** cmdlet changes the properties of a private cloud in Virtual Machine Manager (VMM).

For more information about private clouds, type: `Get-Help New-SCCloud -detailed`.

## EXAMPLES

### Example 1: Update the properties of a private cloud using a job group
```
PS C:\> $Guid = [System.Guid]::NewGuid()
PS C:\> $Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $CapabilityProfile = Get-SCCapabilityProfile -Profilename "HyperV"
PS C:\> Set-SCCloudCapacity -JobGroup $Guid -StorageLimited $True -StorageGB 500 -VirtualMachinesLimited $True -VirtualMachines 50 -VirtualCPUCountLimited $True -VirtualCPUCount 100
PS C:\> Set-SCCloud -Cloud $Cloud -AddCapabilityProfile $CapabilityProfile -JobGroup $Guid -Description "Updated description for Cloud01"
```

The first command creates a new GUID and stores it in the $Guid variable.
Subsequent commands that include this GUID are collected into a single job group.

The second command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The third command gets the Hyper-V capability profile object and stores the object in the $CapabilityProfile variable.

The fourth command sets the following limits on the cloud capacity dimensions: 500 GB storage, 50 virtual machines, and 100 CPUs.
Using the *JobGroup* parameter specifies that this command will not run until just before the final command that includes the JobGroup with the same GUID.

The last command adds the capability profile stored in $CapabilityProfile to Cloud01, updates the description for Cloud01, and sets the cloud capacity properties on Cloud01 using the settings specified in the fourth command.
This command uses the JobGroup parameter to run Set-SCCloudCapacity just before **Set-SCCloud** runs so that the settings will be assocated with the specified private cloud.

## PARAMETERS

### -AddCapabilityProfile
Specifies one or more capability profile objects that this cmdlet adds.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.CapabilityProfile]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddCloudResource
Specifies one or more cloud resources that this cmdlet adds to a private cloud.
Resources that you can add to a private cloud include: Load Balancer, Logical Network, Static IP Address Pool, Storage Pool, and VIP Template.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ClientObject]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddReadOnlyLibraryShare
Specifies one or more read-only library shares that this cmdlet adds to a private cloud.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.LibraryShare]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddVMHostGroup
Specifies one or more host groups to add to an existing host group array or private cloud.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.HostGroup]
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description for the specified object.

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

### -ReadWriteLibraryPath
Specifies a writable library path to which virtual machines can be stored.

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

### -RemoveCapabilityProfile
Specifies one or more capability profile objects that this cmdlet removes.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.CapabilityProfile]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveCloudResource
Specifies one or more cloud resources that this cmdlet removes from a private cloud.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ClientObject]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveReadOnlyLibraryShare
Specifies a read-only library share that this cmdlet removes.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.LibraryShare]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveVMHostGroup
Specifies one or more host groups that this cmdlet removes from a host group array or private cloud.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.HostGroup]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md)

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[New-SCCloud]()

[Remove-SCCloud]()

[Set-SCCloudCapacity](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloudCapacity.md)

