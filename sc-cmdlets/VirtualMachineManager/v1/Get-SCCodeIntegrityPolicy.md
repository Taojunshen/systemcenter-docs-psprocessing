---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCCodeIntegrityPolicy.md
schema: 2.0.0
ms.assetid: 05ED6975-E3CB-4DF8-A2AA-056FCBF197B3
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCodeIntegrityPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCodeIntegrityPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCodeIntegrityPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCodeIntegrityPolicy

## SYNOPSIS
Gets a code integrity policy.

## SYNTAX

### All (Default)
```
Get-SCCodeIntegrityPolicy [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### GetByName
```
Get-SCCodeIntegrityPolicy -Name <String> [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ID
```
Get-SCCodeIntegrityPolicy [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCodeIntegrityPolicy** cmdlet gets a code integrity policy in Virtual Machine Manager (VMM).

## EXAMPLES

### 1:
```

```

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
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

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
Specifies the name of the code integrity policy to get.

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

[New-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/New-SCCodeIntegrityPolicy.md)

[Remove-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/Remove-SCCodeIntegrityPolicy.md)

[Set-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/Set-SCCodeIntegrityPolicy.md)

