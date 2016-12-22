---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 99CAC7B0-2FE3-4043-AAAE-3B2F846F426A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCExternalJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCExternalJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCExternalJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCExternalJob

## SYNOPSIS
Creates a new external job in VMM.

## SYNTAX

```
New-SCExternalJob [-VMMServer <ServerConnection>] [-Name] <String> [-ResultObject <ClientObject>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCExternalJob** cmdlet creates external jobs in Virtual Machine Manager (VMM).

External jobs add non-VMM jobs to the jobs view in the VMM console.
These jobs are typically used to allow other applications integrating with VMM to serve status updates into the console so that users of the console can see the updates.
For example, if you create an add-in, you might use external jobs to provide the status of work completed on another system.

## EXAMPLES

### Example 1: Create an external job
```
PS C:\> $VMMObject = Get-SCVirtualMachine -Name "VM01"
PS C:\> New-SCExternalJob -Name "ExternalJob01" -ResultObject $VMMObject
```

The first command gets the virtual machine object named VM01 and stores the object in the $VMMObject variable.
The object in this command can be any VMM object for which you are creating a job.

The second command creates an external job named ExternalJob01 and relates the job to VM01 which is stored in the $VMMObject variable.

## PARAMETERS

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

### -ResultObject
Specifies the object to which a new external job is related.

```yaml
Type: ClientObject
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Task
This cmdlet returns a **Task** object.

## NOTES

## RELATED LINKS

[Set-SCExternalJob](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCExternalJob.md)

