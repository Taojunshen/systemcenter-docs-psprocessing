---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCloud.md
schema: 2.0.0
ms.assetid: 7FBBC23F-ABB1-4B0A-BBC9-77B6CB31460F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloudCapacity.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloudCapacity.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloudCapacity.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCCloudCapacity

## SYNOPSIS
Modifies the cloud capacity settings for a private cloud.

## SYNTAX

### FromValues
```
Set-SCCloudCapacity -CloudCapacity <CloudCapacity> [-CPUCount <UInt32>] [-UseCPUCountMaximum <Boolean>]
 [-MemoryMB <UInt32>] [-UseMemoryMBMaximum <Boolean>] [-StorageGB <UInt32>] [-UseStorageGBMaximum <Boolean>]
 [-CustomQuotaCount <UInt32>] [-UseCustomQuotaCountMaximum <Boolean>] [-VMCount <UInt32>]
 [-UseVMCountMaximum <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### JobGroupParamSet
```
Set-SCCloudCapacity [-CPUCount <UInt32>] [-UseCPUCountMaximum <Boolean>] [-MemoryMB <UInt32>]
 [-UseMemoryMBMaximum <Boolean>] [-StorageGB <UInt32>] [-UseStorageGBMaximum <Boolean>]
 [-CustomQuotaCount <UInt32>] [-UseCustomQuotaCountMaximum <Boolean>] [-VMCount <UInt32>]
 [-UseVMCountMaximum <Boolean>] [-VMMServer <ServerConnection>] -JobGroup <Guid> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCCloudCapacity** cmdlet modifies the cloud capacity settings for a private cloud in Virtual Machine Manager (VMM).
You can update the following cloud capacity dimensions: 

- virtual machines
- virtual CPUs 
- custom quota points
- storage (GB) 
- memory (MB) 

Alternatively, you can set any or all of the dimensions to use the maximum capacity.

## EXAMPLES

### Example 1: Change the cloud capacity properties of a specified cloud
```
PS C:\>$Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $CloudCapacity = Get-SCCloudCapacity -Cloud $Cloud
PS C:\> Set-SCCloudCapacity -CloudCapacity $CloudCapacity -VirtualCPUCountLimited $True -VirtualCPUCount 20
```

The first command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The second command gets the cloud capacity for the private cloud stored in $Cloud and stores it in the $CloudCapacity variable.

The last command indicates that there should be a limit placed on the virtual CPU count for the cloud capacity stored in $CloudCapacity, and changes the virtual CPU count capacity to 20.

### Example 2: Change the cloud capacity properties of a specific private cloud using a job group
```
PS C:\>$Guid = [System.Guid]::NewGuid()
PS C:\> $Cloud = Get-SCCloud -Name "Cloud02"
PS C:\> $CloudCapacity = Get-SCCloudCapacity -Cloud $Cloud
PS C:\> Set-SCCloudCapacity -JobGroup $Guid -VirtualMachinesLimited $True -VirtualMachines 50 -VirtualCPUCountLimited $True -VirtualCPUCount 100 -StorageLimited $True -StorageGB 500
PS C:\> Set-SCCloud -JobGroup $Guid -Cloud $Cloud
```

The first command creates a new GUID and stores it in the $Guid variable.
Subsequent commands that include this GUID are collected into a single job group.

The second command gets the private cloud object named Cloud02 and stores the object in the $Cloud variable.

The third command gets the cloud capacity object for the private cloud stored in $cloud and stores the object in the $CloudCapacity variable.

The fourth command sets a limit of 50 virtual machines, 100 virtual CPUs and 500 GB of storage on the cloud capacity.
Using the *JobGroup* parameter specifies that this command will not run until just before the final command that includes the JobGroup with the same GUID.

The last command sets the capacity properties on the private cloud stored in $Cloud using the settings that were specified in the fourth command.
This command uses the *JobGroup* parameter to run **Set-SCCloudCapacity** just before Set-SCCloud runs so that the settings will be assocated with the specified private cloud.

## PARAMETERS

### -CPUCount
Specifies the number of virtual CPUs for a user role quota or cloud capacity.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CloudCapacity
Specifies a cloud capacity object.

```yaml
Type: CloudCapacity
Parameter Sets: FromValues
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomQuotaCount
Specifies the number of custom quota points for a user role quota or cloud capacity.

```yaml
Type: UInt32
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
Parameter Sets: JobGroupParamSet
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

### -MemoryMB
Specifies the amount of memory in megabytes (MB) for a user role quota or cloud capacity.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### -StorageGB
Specifies the amount of storage in gigabytes (GB) for a user role quota or cloud capacity.
This storage amount does not include library storage.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCPUCountMaximum
Indicates whether the maximum number of virtual CPUs is allowed for a user role or cloud capacity.
When this parameter is used, no quota is enforced for the virtual CPU dimension.

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

### -UseCustomQuotaCountMaximum
Indicates whether the maximum number of custom quota points is allowed for a user role or cloud capacity.
When this parameter is used, no quota is enforced for the custom quota dimension.

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

### -UseMemoryMBMaximum
Indicates whether the maximum amount of memory, in megabytes (MB), is allowed for a user role or cloud capacity.
When this parameter is used, no quota is enforced for the memory dimension.

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

### -UseStorageGBMaximum
Indicates whether the maximum amount of storage, in gigabytes (GB), is allowed for a user role or cloud capacity.
When this parameter is used, no quota is enforced for the storage dimension.

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

### -UseVMCountMaximum
Indicates whether the maximum number of virtual machines is allowed for a user role or cloud capacity.
When this parameter is used, no quota is enforced for the virtual machine dimension.

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

### -VMCount
Specifies the number of virtual machines for a user role quota or cloud capacity.

```yaml
Type: UInt32
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[Set-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCloud.md)

[Get-SCCloudCapacity](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloudCapacity.md)

