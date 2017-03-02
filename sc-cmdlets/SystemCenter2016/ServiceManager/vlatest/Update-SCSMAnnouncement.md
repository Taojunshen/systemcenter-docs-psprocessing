---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B43C677D-967C-45E0-B7D4-C8D2BF4223E0
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMAnnouncement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMAnnouncement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMAnnouncement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Update-SCSMAnnouncement

## SYNOPSIS
Updates the properties of an announcement for Service Manager.

## SYNTAX

```
Update-SCSMAnnouncement [-Announcement] <EnterpriseManagementInstance[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMAnnouncement** cmdlet updates the properties of an announcement in Service Manager.

## EXAMPLES

### Example 1: Extend the expiration date of an announcement
```
PS C:\>$Announcement = Get-SCSMAnnouncement -Title "33"
PS C:\> $Announcement.ExpirationDate = ([datetime]::Now.AddMonths(6))
PS C:\> Update-SCSMAnnouncement -Announcement $announcement
PS C:\> Get-SCSMAnnouncement -Title "33"
TimeAdded            Title            Priority  ExpirationDate
---------            -----            --------  --------------
3/31/2010 6:55:45 PM Announcement 33  Medium    3/31/2011 11:55:45 AM
```

The first command gets an announcement titled 33 by using the Get-SCSMAnnouncement cmdlet.
The command stores that announcement in the $Announcement variable.

The second command uses standard dot syntax to assign a new value to the **ExpirationDate** property of $Announcement.
The new value is six months in the future.

The third command updates the announcement to be the current value of $Announcement.

The final command displays the value of the announcement titled 33 to very your changes.

## PARAMETERS

### -Announcement
Specifies an instance of an announcement to update.

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

### -PassThru
Indicates that this cmdlet returns the announcement that it updates.
You can pass this object to other cmdlets.

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
You can pipe an announcement object to the *Announcement* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMAnnouncement.md)

[New-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMAnnouncement.md)

[Remove-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAnnouncement.md)

