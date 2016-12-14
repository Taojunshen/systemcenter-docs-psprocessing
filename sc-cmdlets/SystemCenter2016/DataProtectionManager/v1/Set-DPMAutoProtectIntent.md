---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMAutoProtectIntent.md
schema: 2.0.0
ms.assetid: AF639F32-8201-4FA8-87F6-3AC38E2D8C59
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMAutoProtectIntent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMAutoProtectIntent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMAutoProtectIntent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMAutoProtectIntent

## SYNOPSIS
Turns DPM auto-protection on or off for a SQL Server instance.

## SYNTAX

```
Set-DPMAutoProtectIntent [-ProtectionGroup] <ProtectionGroup> [-SQLInstanceName] <String[]>
 [-AutoProtectIntent] <AutoProtectionIntent> [-ProductionServer] <ProductionServer> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMAutoProtectIntent** cmdlet turns System Center 2016 - Data Protection Manager (DPM) auto-protection on or off for a Microsoft SQL Server data management software instance.
When you use auto-protection for a SQL Server instance, DPM identifies and protects new databases added to that instance.
To change the auto-protection setting, specify the SQL Server instance, the protection group that it belongs to, and a production server.

When you first add a SQL Server instance to a protection group, the DPM server enables auto-protection for that instance.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AutoProtectIntent
Specifies whether the cmdlet turns auto-protection on or off.

The acceptable values for this parameter are: Enable and Disable.

```yaml
Type: AutoProtectionIntent
Parameter Sets: (All)
Aliases: 
Accepted values: Enable, Disable

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductionServer
Specifies a computer on which a DPM protection agent is installed.

```yaml
Type: ProductionServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SQLInstanceName
Specifies an array of names of SQL Server instances.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMAutoProtectIntent](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMAutoProtectIntent.md)

[Start-DPMAutoProtection](xref:SystemCenter2016/DataProtectionManager/v1/Start-DPMAutoProtection.md)

