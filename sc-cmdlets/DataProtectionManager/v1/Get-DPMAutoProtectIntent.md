---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMAutoProtectIntent.md
schema: 2.0.0
ms.assetid: 1F81FBA4-873D-4142-9BC9-D7759251EA5A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAutoProtectIntent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAutoProtectIntent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMAutoProtectIntent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMAutoProtectIntent

## SYNOPSIS
Gets the auto-protection setting for a SQL Server instance.

## SYNTAX

### DPMServer (Default)
```
Get-DPMAutoProtectIntent [[-DPMServerName] <String>] [-SQLInstanceName] <String> [<CommonParameters>]
```

### ProtectionGroup
```
Get-DPMAutoProtectIntent [-SQLInstanceName] <String> [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMAutoProtectIntent** cmdlet gets the System Center 2016 - Data Protection Manager (DPM) auto-protection setting for a Microsoft SQL Server data management software instance.
When you use auto-protection for a SQL Server instance, DPM identifies and protects new databases added to that instance.
To see the current settings for auto-protection, specify the SQL Server instance, and either the protection group that it belongs to or the name of a DPM server.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: DPMServer
Aliases: ComputerName, CN

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets a setting.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: ProtectionGroup
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SQLInstanceName
Specifies the name of a SQL Server instance.

```yaml
Type: String
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Set-DPMAutoProtectIntent](xref:DataProtectionManager/v1/Set-DPMAutoProtectIntent.md)

[Start-DPMAutoProtection](xref:DataProtectionManager/v1/Start-DPMAutoProtection.md)

