---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 07B5DD22-DA15-4521-862A-DE99D32B40F7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaModule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaModule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaModule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SmaModule

## SYNOPSIS
Imports a module into SMA.

## SYNTAX

```
Import-SmaModule -Path <String> -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SmaModule** cmdlet imports a module into Service Management Automation (SMA).
A module is a compressed file, with a .zip extension, that contains a folder which includes one of the following file types:

- A Windows PowerShell module (psm1 file).
- A Windows PowerShell module manifest (psd1 file).
- An assembly (dll file).

The names of the zip file, the folder in the zip file, and file in the folder must match.

## EXAMPLES

### Example 1: Import a module
```
PS C:\> Import-SmaModule -WebServiceEndpoint "https://contoso.com/app01" -Path ".\MyModule.zip"
```

This command imports the module named MyModule from the specified module path.

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

### -Path
Specifies the path to a module.
The path must point to a compressed file, with a .zip extension, that contains a folder which includes one of the following file types:

- A Windows PowerShell module (psm1 file).
- A Windows PowerShell module manifest (psd1 file).
- An assembly (dll file).

The names of the zip file, the folder in the zip file, and the file in the folder (.psm1, psd.1, or .dll) must match.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ModulePath

Required: True
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SmaModule](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaModule.md)

[Remove-SmaModule](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaModule.md)

