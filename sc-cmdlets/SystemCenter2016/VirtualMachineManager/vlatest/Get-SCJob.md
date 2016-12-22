---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 486031E1-6280-4A82-AB22-ED6864EFBBC8
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCJob

## SYNOPSIS
Gets VMM job objects.

## SYNTAX

### NewestJobs (Default)
```
Get-SCJob [-VMMServer <ServerConnection>] [[-Name] <String>] [-Full] [-Newest <Int32>] [-Job <Task>]
 [-ID <Guid>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### AllJobs
```
Get-SCJob [-VMMServer <ServerConnection>] [[-Name] <String>] [-Full] [-All] [-Job <Task>] [-ID <Guid>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### RunningJobs
```
Get-SCJob [-VMMServer <ServerConnection>] [[-Name] <String>] [-Running] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCJob** cmdlet gets one or more Virtual Machine Manager (VMM) job objects on the VMM server.
A job is a series of steps that are performed sequentially to complete an action in the VMM environment.
You can retrieve job objects based on specified criteria.

In VMM, you can group a series of jobs and run them together as a set.
For example, a complex action in VMM, such as creating a template, might incorporate a series of jobs, known as a job group.
For examples that demonstrate how to use job groups, see the following cmdlets: New-SCVMTemplate, New-SCHardwareProfile, New-SCVirtualDiskDrive, New-SCVirtualDVDDrive, New-SCVirtualMachine, and Set-SCVirtualCOMPort.

## EXAMPLES

### Example 1: Get all running jobs
```
PS C:\> Get-Job -Running
```

This command retrieves all running jobs.

### Example 2: Get all failed jobs
```
PS C:\> $VMMJobs = Get-SCJob | where { $_.Status -eq "Failed" } | Format-List -Property Name, ID, Status
PS C:\> $VMMJobs
```

The first command gets all job objects with a status of Failed, and then uses the pipeline operator to pass each object to the Format-List cmdlet, which stores the name, ID, and Status in the $VMMJobs variable.

The second command displays the information stored in $VMMJobs to the user (in this case, that is the name, ID, and Status of each running job).

### Example 3: Get information about the .NET type, methods, and properties of VMM job objects
```
PS C:\> Get-SCJob | Get-Member
```

This command uses the **Get-Member** cmdlet to display the .NET type, properties, methods, and events for **Get-SCJob**.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: AllJobs
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Full
Indicates that the cmdlet returns the job object with an audit record.

```yaml
Type: SwitchParameter
Parameter Sets: NewestJobs, AllJobs
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: NewestJobs, AllJobs
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies a VMM job object.

```yaml
Type: Task
Parameter Sets: NewestJobs, AllJobs
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
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Newest
Returns all jobs created in the last specified number of hours, or returns the specified number of most recent software updates. 



Example format to return all jobs created in the last 48 hours: `Get-SCJob -Newest 48`


Example format to return the 10 newest updates: `Get-SCUpdate -Newest 10`

```yaml
Type: Int32
Parameter Sets: NewestJobs
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

### -Running
Indicates that all running jobs are returned.

```yaml
Type: SwitchParameter
Parameter Sets: RunningJobs
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Job
This cmdlet returns a **Job** object.

## NOTES

## RELATED LINKS

[Find-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Find-SCJob.md)

[Restart-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCJob.md)

[Stop-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCJob.md)

