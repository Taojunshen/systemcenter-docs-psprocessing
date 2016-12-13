---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=323489
schema: 2.0.0
ms.assetid: 9F9138F2-4489-4FFB-A10B-2A073F9809D9
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Set-SmaLicense.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Set-SmaLicense.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceManagementAutomation/v1/Set-SmaLicense.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SmaLicense

## SYNOPSIS
Updates the SMA product key.

## SYNTAX

```
Set-SmaLicense [-ProductKey] <String> -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmaLicense** cmdlet updates the Service Management Automation (SMA) product key.
If you are using an evaluation version of SMA, use this cmdlet to provide a product key to upgrade to the full product version.

## EXAMPLES

### Example 1: Provide a Service Management Automation product key
```
PS C:\>Set-SmaLicense -WebServiceEndopoint "https://localhost" -ProductKey "XXXX-XXXXX-XXXXX-XXXXX"
```

This command provides a product key to SMA.

## PARAMETERS

### -AuthenticationType
Specifies the authentication type.
Valid values are: 

- Basic
- Windows

The default value for this parameter is Windows.
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

### -ProductKey
Specifies the SMA product key.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebServiceEndpoint
Specifies the endpoint, as a URL, of the SMA web service.
You must include the protocol, for example, http:// or https://.

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

[Get-SmaLicense](xref:ServiceManagementAutomation/v1/Get-SmaLicense.md)

