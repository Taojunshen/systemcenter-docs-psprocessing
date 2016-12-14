---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225331
schema: 2.0.0
ms.assetid: B2ED3E2C-4AF7-4206-8479-A54288B95A0E
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMQueue.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMQueue.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Get-SCSMQueue.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMQueue

## SYNOPSIS
Retrieves queues that are defined in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMQueue [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMQueue [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMQueue** cmdlet retrieves queues that are defined in Service Manager.

## EXAMPLES

### Example 1: Get all available queues
```
PS C:\>Get-SCSMQueue
WorkItemType DisplayName Description        ManagementPackName                              TimeAdded             LastModified
------------ ----------- -----------        ------------------                              ---------             ------------
Incident     queue1      just a description ServiceManager.IncidentManagement.Configuration 12/1/2010 12:48:26 AM 12/1/2010 12:48:26 AM
```

This command retrieves all the queues that are available in Service Manager.

### Example 2: Get queues by using a display name
```
PS C:\>Get-SCSMQueue -DisplayName "queue*"
WorkItemType DisplayName Description        ManagementPackName                              TimeAdded             LastModified
------------ ----------- -----------        ------------------                              ---------             ------------
Incident     queue1      just a description ServiceManager.IncidentManagement.Configuration 12/1/2010 12:48:26 AM 12/1/2010 12:48:26 AM
```

This command retrieves the queues in which *DisplayName* is like queue.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the Credential parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
Specifies the display name of the queue to retrieve.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the queue to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies the object that represents the session to a Service Manager management server.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### WorkItemGroup
This cmdlet returns a unique **WorkItemGroup** queue object.

## NOTES

## RELATED LINKS

