---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B4FE0C37-16CF-42BF-9343-66B52046BE49
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMTape

## SYNOPSIS
Returns tapes in the library.

## SYNTAX

### Library
```
Get-DPMTape [-DPMLibrary] <Library[]> [<CommonParameters>]
```

### RecoverySourceLocation
```
Get-DPMTape [-RecoveryPointLocation] <RecoverySourceLocation[]> [<CommonParameters>]
```

### ProtectionGroup
```
Get-DPMTape [-ProtectionGroup] <ProtectionGroup[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMTape** cmdlet returns tapes in the library.
In System Center 2016 - Data Protection Manager (DPM), a library refers to multi-drive tape hardware and stand-alone tape drives.

## EXAMPLES

### Example 1: Retrieve a list of tapes for a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> Get-DPMTape -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the server, and then stores it in the $DpmLibrary variable.

The second command uses the **Get-DPMTape** cmdlet to return the list of tapes on Contoso-DPMServer.

## PARAMETERS

### -DPMLibrary
Specifies an array of DPM library objects that this cmdlet gets.
The library objects can be multi-drive tape hardware or stand-alone tape drives.

```yaml
Type: Library[]
Parameter Sets: Library
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies an array of protection groups for which this cmdlet gets tapes.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.
A protection group consists of data sources, such as volumes or shares, that have a common protection configuration and schedule.

```yaml
Type: ProtectionGroup[]
Parameter Sets: ProtectionGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointLocation
Specifies an array of recovery point locations for which this cmdlet gets tapes.
To obtain a recovery point location object, use the Get-DPMRecoveryPointLocation cmdlet.
A recovery point is a copy of a replica stored on a DPM server.
You can specify multiple locations for recovery items that exist on a disk and a tape, or on multiple tapes.

```yaml
Type: RecoverySourceLocation[]
Parameter Sets: RecoverySourceLocation
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Tape

## NOTES

## RELATED LINKS

[Add-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMTape.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Remove-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMTape.md)

[Set-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMTape.md)

