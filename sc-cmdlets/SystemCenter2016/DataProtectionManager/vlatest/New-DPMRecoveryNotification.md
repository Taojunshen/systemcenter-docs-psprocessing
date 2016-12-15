---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./New-DPMRecoveryOption.md
schema: 2.0.0
ms.assetid: D20BBD26-D268-412C-833D-F05D9406A817
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryNotification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryNotification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryNotification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMRecoveryNotification

## SYNOPSIS
Creates a notification object.

## SYNTAX

```
New-DPMRecoveryNotification [-NotificationType] <NotificationType> [-NotificationIdList] <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMRecoveryNotification** cmdlet creates a notification object that System Center 2016 - Data Protection Manager (DPM) uses for recovery.
DPM currently supports only email notifications.

## EXAMPLES

### Example 1: Create a notification object
```
PS C:\>New-DPMRecoveryNotification -NotificationType email -NotificationIdList "Elisa.Daugherty@contoso.com"
```

This command creates an email notification for an event that DPM sends to Elisa.Daugherty@contoso.com.

## PARAMETERS

### -NotificationIdList
Specifies an array of IDs to which the recovery sends notifications.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationType
Specifies the type of notification.
Currently, the only valid value is email.

```yaml
Type: NotificationType
Parameter Sets: (All)
Aliases: 
Accepted values: Email

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Notification

## NOTES

## RELATED LINKS

[New-DPMRecoveryOption](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryOption.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

