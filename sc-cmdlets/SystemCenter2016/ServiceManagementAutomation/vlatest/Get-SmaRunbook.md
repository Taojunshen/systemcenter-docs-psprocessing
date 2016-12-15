---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=306445
schema: 2.0.0
ms.assetid: C12019AC-E9DE-4B87-BA09-D81CD7DE2FB4
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaRunbook.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaRunbook.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaRunbook.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SmaRunbook

## SYNOPSIS
Gets an SMA runbook.

## SYNTAX

### GetAll (Default)
```
Get-SmaRunbook -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookId
```
Get-SmaRunbook [-Id <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookName
```
Get-SmaRunbook [-Name <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaRunbook** cmdlet gets one or more Service Management Automation (SMA) runbooks.
By default, all runbooks are returned.
To get a specific runbook, specify its name or ID.

## EXAMPLES

### Example 1: Get a runbook by its name
```
PS C:\> Get-SmaRunbook -Name "Runbk01" -WebServiceEndpoint "https://contoso.com/app01"
```

This command gets the runbook named Runbk01 from the SMA web service that has endpoint URL https://contoso.com/app01.

## PARAMETERS

### -AuthenticationType
Specifies the authentication type.
Valid values are: 

- Basic
- Windows

The default value is Windows.
If you use Basic authentication, you must provide credentials by using the *Credential* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Basic, Windows

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object for the connection to the SMA web service.
To obtain a credential object, use the Get-Credential cmdlet.
For more information, type `Get-Help Get-Credential`.

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

### -Id
Specifies an array of runbook IDs that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: ByRunbookId
Aliases: RunbookId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of runbook names that this cmdlet gets.

```yaml
Type: String[]
Parameter Sets: ByRunbookName
Aliases: RunbookName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the port number of the SMA web service.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServiceEndpoint
Specifies the endpoint, as a URL, of the SMA web service.
You must include the protocol, for instance, http:// or https://.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Edit-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Edit-SmaRunbook.md)

[Import-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaRunbook.md)

[Publish-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Publish-SmaRunbook.md)

[Remove-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaRunbook.md)

[Start-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Start-SmaRunbook.md)

