---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4D294EC6-AE07-4677-934E-315BACBE824D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStep.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStep.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStep.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStep

## SYNOPSIS
Gets the steps for the specified VMM job.

## SYNTAX

```
Get-SCStep [-Job] <Task> [-Name <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStep** cmdlet gets the steps for the specified Virtual Machine Manager (VMM) job.

A job is composed of one or more steps, each of which has its own status.
An earlier step must complete or be skipped before the next step runs.

## EXAMPLES

### Example 1: Get all steps for a specified job
```
PS C:\> $Job = Get-SCJob -ID "cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177"
PS C:\> $Steps = Get-SCStep -Job $Job
PS C:\> $Steps.Children
```

The first command gets the VMM job object with the ID cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177 and stores the object in the $Job variable.

The second command gets the step object for the VMM job in $Job.

The last command lists information about each step for the VMM job, including a description of the step, its progress, and its status.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Step
This cmdlet returns a **Step** object.

## NOTES

## RELATED LINKS

[Get-SCJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCJob.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

