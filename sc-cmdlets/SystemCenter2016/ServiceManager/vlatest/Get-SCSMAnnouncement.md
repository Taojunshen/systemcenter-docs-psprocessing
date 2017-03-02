---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BB850617-4538-4985-AE60-1CD224CB2DA9
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAnnouncement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAnnouncement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAnnouncement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMAnnouncement

## SYNOPSIS
Retrieves announcements that are defined in Service Manager.

## SYNTAX

```
Get-SCSMAnnouncement [-Id <String>] [-DisplayName <String>] [-Title <String>] [-Priority <String>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMAnnouncement** cmdlet retrieves announcements that are defined in Service Manager.
This includes announcements that have been published and that have expired.
You can restrict the results by providing a filter or criteria.
Use the **Where-Object** cmdlet to retrieve only announcements that are active or that have expired.
The *Title*, *Id*, and *Name* parameters are additive.
If you use the *Title* and the *Id* parameters, only those announcements which satisfy both parameters are returned.

## EXAMPLES

### Example 1: Get all announcements
```
C:\PS>Get-SCSMAmannouncement
TimeAdded                     Title                         Priority                      ExpirationDate
---------                     -----                         --------                      --------------
3/31/2010 6:55:44 PM          Announcement 8                Critical                      3/31/2011 11:55:44 AM
3/31/2010 6:55:44 PM          Announcement 24               Critical                      3/29/2010 12:01:38 PM
3/31/2010 6:55:46 PM          Announcement 75               Low                           3/29/2010 12:01:38 PM
3/31/2010 6:55:46 PM          Announcement 78               Low                           3/31/2011 11:55:46 AM
3/31/2010 6:55:46 PM          Announcement 61               Medium                        3/31/2011 11:55:46 AM
3/31/2010 6:55:46 PM          Announcement 59               Medium                        3/31/2011 11:55:46 AM
3/31/2010 6:55:45 PM          Announcement 33               Medium                        3/31/2011 11:55:45 AM
3/31/2010 6:55:46 PM          Announcement 63               Medium                        3/31/2011 11:55:46 AM
3/31/2010 6:55:44 PM          Announcement 28               Critical                      3/31/2011 11:55:44 AM
3/31/2010 6:55:47 PM          Announcement 99               Low                           3/31/2011 11:55:47 AM
```

This command retrieves all announcements that are defined in Service Manager.

### Example 2: Get announcements for an ID
```
C:\PS>Get-SCSMAmannouncement -Id "008"
TimeAdded                     Title                         Priority                      ExpirationDate
---------                     -----                         --------                      --------------
3/31/2010 6:55:44 PM          Announcement 8                Critical                      3/31/2011 11:55:44 AM
```

This command retrieves the announcement in which the ID equals 008.

### Example 3: Get announcements for a title
```
C:\PS>Get-SCSMAmannouncement -Title "33"
TimeAdded                     Title                         Priority                      ExpirationDate
---------                     -----                         --------                      --------------
3/31/2010 6:55:45 PM          Announcement 33               Medium                        3/31/2011 11:55:45 AM
```

This command retrieves the announcement in which the title equals 33.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of an announcement.
You can specify a regular expression.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the announcement to retrieve.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Priority
Specifies the priority of an announcement.
This allows you to retrieve announcements of a specified priority.
Allowed values are Medium, Critical, Low, and custom values.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Represents the session to the Service Manager server.

```yaml
Type: Connection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Title
Specifies the title of the announcement.
This parameter accepts a wildcard character.

```yaml
Type: String
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Announcement.Item
The output of this cmdlet is a list of announcements.

## NOTES

## RELATED LINKS

[New-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMAnnouncement.md)

[Update-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMAnnouncement.md)

[Remove-SCSMAnnouncement](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAnnouncement.md)

