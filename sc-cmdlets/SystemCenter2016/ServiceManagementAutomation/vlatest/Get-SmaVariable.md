---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CF74A435-212E-4775-9583-4EA5C0992E34
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaVariable.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaVariable.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaVariable.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SmaVariable

## SYNOPSIS
Gets an SMA variable.

## SYNTAX

```
Get-SmaVariable [-Name <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaVariable** cmdlet gets one or more Service Management Automation (SMA) variables.
Specify the web service endpoint and, if necessary, a port number.
By default, all variables are returned.
To get a specific variable, specify its name.

## EXAMPLES

### Example 1: Get a variable
```
PS C:\> Get-SmaVariable -WebServiceEndpoint "https://contoso.com/app01" -Name "Variable83"
```

This command gets the variable named Variable83 from the specified web service endpoint.

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

### -Name
Specifies the name of a variable.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

[Remove-SmaVariable](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaVariable.md)

[Set-SmaVariable](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaVariable.md)

