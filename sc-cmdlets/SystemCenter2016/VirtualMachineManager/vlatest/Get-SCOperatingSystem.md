---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EF1FE966-F8AD-4A1A-BB27-F8E5174441B8
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOperatingSystem

## SYNOPSIS
Gets valid operating system objects from the VMM database.

## SYNTAX

### All (Default)
```
Get-SCOperatingSystem [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ID
```
Get-SCOperatingSystem [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

### Profile
```
Get-SCOperatingSystem [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOperatingSystem** cmdlet gets one or more operating system objects from the Virtual Machine Manager (VMM) database.
An operating system object is used to identify the operating system that is installed on a particular virtual hard disk.

## EXAMPLES

### Example 1: Get all operating system objects in your VMM environment
```
PS C:\> Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com"
```

This command gets all operating system objects from the VMM database on VMMServer01 and displays information about these operating system objects to the user.

### Example 2: Get all operating system objects in your VMM environment with the specified processor architecture
```
PS C:\> Get-OperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Architecture -eq "amd64"} | Format-Table -Property Name,Architecture
```

This command gets all operating system objects from VMMServer01 and then selects only those operating systems that have an amd64 processor architecture.
The command uses the Format-Table cmdlet to display only the Name and Architecture properties for each selected operating system.

## PARAMETERS

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: Profile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
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
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### OperatingSystem
This cmdlet returns an **OperatingSystem** object.

## NOTES

## RELATED LINKS

[Add-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCOperatingSystem.md)

[Remove-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOperatingSystem.md)

