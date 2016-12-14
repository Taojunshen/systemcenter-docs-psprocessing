---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCCloud.md
schema: 2.0.0
ms.assetid: A9921D55-A461-447F-ADFE-69F2808B471A
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCloudCapacity.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCloudCapacity.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCCloudCapacity.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCloudCapacity

## SYNOPSIS
Gets the cloud capacity for a private cloud.

## SYNTAX

```
Get-SCCloudCapacity [[-Cloud] <Cloud>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCloudCapacity** cmdlet gets the cloud capacity for a private cloud in Virtual Machine Manager (VMM).
Cloud capacity includes settings for the number of virtual machines, number of virtual CPUs, custom quota points, storage, and memory assigned to a private cloud.

## EXAMPLES

### Example 1: Get the cloud capacity for a specified private cloud
```
PS C:\>$Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> Get-SCCloudCapacity -Cloud $Cloud
```

The first command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The second command gets the cloud capacity for the private cloud object stored in $Cloud, and displays information about the cloud capacity to the user.

## PARAMETERS

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

[Set-SCCloud](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCloud.md)

[Set-SCCloudCapacity](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCCloudCapacity.md)

