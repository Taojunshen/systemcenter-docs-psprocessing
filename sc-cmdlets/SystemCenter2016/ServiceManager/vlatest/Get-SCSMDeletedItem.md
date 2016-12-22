---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 71FFC58E-C3C4-474A-8FC0-0ED59B9C92F4
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDeletedItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDeletedItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMDeletedItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMDeletedItem

## SYNOPSIS
Retrieves items that have been marked for deletion in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMDeletedItem [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMDeletedItem [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCSMDeletedItem [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMDeleteditem** cmdlet retrieves items that have been marked for deletion in Service Manager.
You can then use the Restore-SCSMDeletedItem cmdlet to restore these items.

## EXAMPLES

### Example 1: Get deleted items
```
C:\PS>Get-SCSMDeleteditem
UserName  Domain FirstName LastName
--------  ------ --------- --------
Dave.Chew JWT-D4 Dave      Chew
```

This command retrieves deleted items from the Service Manager database.

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
Specifies the display name of the deleted item to retrieve.
You can specify a regular expression.

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
Specifies the ID of the deleted item to retrieve.

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

### -Name
Specifies the name of the deleted item to retrieve.
You can specify a regular expression.

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents a session to a Service Manager management server.

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

### The type of object that is being deleted.
This cmdlet retrieves items that have been marked for deletion from the Service Manager database.

## NOTES

## RELATED LINKS

[Restore-SCSMDeletedItem](xref:SystemCenter2016/ServiceManager/vlatest/Restore-SCSMDeletedItem.md)

