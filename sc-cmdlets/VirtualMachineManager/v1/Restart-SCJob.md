---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Find-SCJob.md
schema: 2.0.0
ms.assetid: 5CC8127C-203E-4A65-B66A-FB75A7DD5295
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Restart-SCJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Restart-SCJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Restart-SCJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Restart-SCJob

## SYNOPSIS
Restarts a failed or canceled VMM job.

## SYNTAX

```
Restart-SCJob [-Job] <Task> [-Credential <VMMCredential>] [-SkipLastFailedStep] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-SCJob** cmdlet restarts one or more Virtual Machine Manager (VMM) jobs that have failed or that have been canceled by a user.
Jobs that are currently running must be canceled before they can be restarted.
All restarted jobs start from the last known good checkpoint before a failure or a cancellation (some jobs have only a single checkpoint).

Restarting a job displays the object properties of the job to the user and shows the Status property as Running.

## EXAMPLES

### Example 1: Restart all jobs that were cancelled on a specific virtual machine
```
PS C:\>$Creds = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Get-SCJob | where { $_.ResultName -eq "VM01" -and $_.Status -eq "Canceled" } | Restart-SCJob -Credential $Creds
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Creds variable.

The second command gets all VMM jobs from the VMM database, selects only jobs on virtual machine VM01 that have been cancelled, and then passes each object to the **Restart-SCJob** cmdlet, which restarts the jobs using the Run As account supplied in $Creds.

### Example 2: Restart a specific job
```
PS C:\>$Creds = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Get-SCJob -ID "cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177" | Restart-SCJob -Credential $Creds
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Creds variable.

The second command gets the VMM job object with ID cb3a0f0a-9fbc-4bd0-a999-3fae8cd77177, and restarts that job using the Run As account supplied in $Creds.

## PARAMETERS

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### -SkipLastFailedStep
Indicates that the last step that failed will not be rerun when a job is restarted.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Job
This cmdlet returns a **Job** object.

## NOTES
* This cmdlet requires a VMM job object, which can be retrieved by using the Get-SCJob cmdlet.

## RELATED LINKS

[Find-SCJob](xref:VirtualMachineManager/v1/Find-SCJob.md)

[Get-SCJob](xref:VirtualMachineManager/v1/Get-SCJob.md)

[Stop-SCJob](xref:VirtualMachineManager/v1/Stop-SCJob.md)

