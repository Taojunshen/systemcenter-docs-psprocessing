---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225395
schema: 2.0.0
ms.assetid: F64219BA-EAC1-4EA8-BF5A-4758ECAB0585
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMAnnouncement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMAnnouncement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Remove-SCSMAnnouncement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMAnnouncement

## SYNOPSIS
Removes an announcement from Service Manager.

## SYNTAX

```
Remove-SCSMAnnouncement [-Announcement] <EnterpriseManagementInstance[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMAnnouncement** cmdlet removes an announcement from Service Manager.

## EXAMPLES

### Example 1: Remove announcements by using a title
```
C:\PS>Get-SCSMAnnouncement | Where-Object { $_.title -match "labor day" } | Remove-SCSMAnnouncement
```

This command removes all announcements with a title that matches the string labor day.
The command uses the **Get-SCSMAnnouncement** cmdlet to get all announcement instances.
The command passes the results to the Where-Object cmdlet, which passes on only those that have titles that match the specified string.
The current cmdlet removes those announcements.

## PARAMETERS

### -Announcement
Specifies instances of announcements.
To obtain an instance, use the Get-SCSMAnnouncement cmdlet.

```yaml
Type: EnterpriseManagementInstance[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### Microsoft.EnterpriseManagement.Core.Cmdlets.Instances.EnterpriseManagementInstance
You can pipe an announcement to the *Announcement* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/Get-SCSMAnnouncement.md)

[New-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/New-SCSMAnnouncement.md)

[Update-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/Update-SCSMAnnouncement.md)

