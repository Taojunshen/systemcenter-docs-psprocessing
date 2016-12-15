---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Find-SCJob.md
schema: 2.0.0
ms.assetid: 9B44F245-07EE-4309-8D4F-98D86DB84D42
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-SCJob

## SYNOPSIS
Stops running VMM jobs.

## SYNTAX

```
Stop-SCJob [-Job] <Task> [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SCJob** cmdlet stops one or more Virtual Machine Manager (VMM) jobs that are running, and returns the object for each job in a stopped state.
If the VMM job is not currently running, this cmdlet has no effect.

## EXAMPLES

### Example 1: Stop all currently running jobs
```
PS C:\>$Job = Get-SCJob | where { $_.Status -eq "Running" }
PS C:\> $Job | Stop-SCJob
```

The first command gets all VMM job objects, passes each job object to the "where" filter to select only the jobs that are currently running, and stores the objects in the $Job object array.

The second command passes each object in $Job to the **Stop-SCJob** cmdlet, which stops each running job.

### Example 2: Stop a specific running job asynchronously
```
PS C:\>$Job = Get-SCJob | where { $_.ResultName -eq "VM01" -and $_.ID -eq "cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177" }
PS C:\> Stop-SCJob -Job $Job
```

The first command gets all VMM job objects and, from the results, selects only the job on VM01 identified by job ID cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177, and then stores thie object in the $Job variable.

The second command stops the job and returns the stopped job object to the user.

## PARAMETERS

### -Job
Specifies a VMM job object.

```yaml
Type: Task
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Task
This cmdlet returns a **Task** object.

## NOTES
* This cmdlet requires a VMM job object, which can be retrieved by using the Get-SCJob cmdlet.

## RELATED LINKS

[Find-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Find-SCJob.md)

[Get-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCJob.md)

[Restart-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Restart-SCJob.md)

