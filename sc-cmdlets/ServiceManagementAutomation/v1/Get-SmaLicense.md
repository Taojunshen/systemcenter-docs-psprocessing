---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=323488
schema: 2.0.0
ms.assetid: F6BCAE34-38AC-451A-89F0-CBE4C7AD8FF5
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaLicense.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaLicense.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaLicense.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SmaLicense

## SYNOPSIS
Gets an SMA license.

## SYNTAX

```
Get-SmaLicense -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaLicense** cmdlet gets Service Management Automation (SMA) licensing information.

## EXAMPLES

### Example 1: Get Service Management Automation licensing information
```
PS C:\>Get-SmaLicense -WebServiceEnddpoint "https://localhost"
```

This command gets SMA licensing information for the SMA service.

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

[Set-SmaLicense](xref:ServiceManagementAutomation/v1/Set-SmaLicense.md)
