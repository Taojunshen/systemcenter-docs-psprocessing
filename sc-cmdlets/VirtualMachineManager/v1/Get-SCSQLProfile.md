---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCSQLProfile.md
schema: 2.0.0
ms.assetid: 651232B3-A461-40E9-9AEB-20CC6B14441E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSQLProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSQLProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCSQLProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSQLProfile

## SYNOPSIS
Gets a SQL Server profile.

## SYNTAX

### GetAll (Default)
```
Get-SCSQLProfile [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### GetByName
```
Get-SCSQLProfile [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### GetByVMTemplate
```
Get-SCSQLProfile [-VMMServer <ServerConnection>] -VMTemplate <Template> [<CommonParameters>]
```

### All
```
Get-SCSQLProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCSQLProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSQLProfile** cmdlet gets a Microsoft SQL Server profile.

## EXAMPLES

### Example 1: Get a ssNoVersion profilessNoVersion
```
PS C:\>Get-SCSQLProfile -Name "SQLProfile01"
```

This command gets the SQL Server profile named SQLProfile01.

The second command displays information about the SQL Server profile object stored in $SQLProfile.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the unique ID of the SQL Server profile that this cmdlet gets.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the SQL Server profile that this cmdlet gets.

```yaml
Type: String
Parameter Sets: GetByName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies the VMM server on which this cmdlet operates.

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

### -VMTemplate
Specifies a VMM template that is used to create virtual machines.
This cmdlet gets SQL Server profiles for the template that this parameter specifies.

```yaml
Type: Template
Parameter Sets: GetByVMTemplate
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SQLProfile
This cmdlet returns a **SQLProfile** object.

## NOTES

## RELATED LINKS

[New-SCSQLProfile](xref:VirtualMachineManager/v1/New-SCSQLProfile.md)

[Remove-SCSQLProfile](xref:VirtualMachineManager/v1/Remove-SCSQLProfile.md)

[Set-SCSQLProfile](xref:VirtualMachineManager/v1/Set-SCSQLProfile.md)

