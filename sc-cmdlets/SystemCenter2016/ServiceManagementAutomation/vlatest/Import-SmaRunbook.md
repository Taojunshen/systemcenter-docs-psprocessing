---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4B08643E-BD68-4C8B-9F5C-1C7E5CB8ECC2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaRunbook.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaRunbook.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaRunbook.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Import-SmaRunbook

## SYNOPSIS
Imports a runbook into SMA.

## SYNTAX

```
Import-SmaRunbook -Path <String> [-Tags <String>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SmaRunbook** cmdlet imports a runbook into Service Management Automation (SMA).
The runbook must be a Windows PowerShell script (.ps1) file.
Specify the path of a runbook and the web service endpoint.
If necessary, specify the port of the SMA web service.
The runbook can be of type PowerShell Script or Workflow.

## EXAMPLES

### Example 1: Import a runbook into Service Management Automation
```
PS C:\> Import-SmaRunbook -Path "./Runbook01.ps1" -WebServiceEndpoint "https://contoso.com/app01"
```

This command imports the runbook file named Runbook01.ps1 into the SMA web service that has endpoint URL https://contoso.com/app01.

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
Specifies the path to a runbook.

```yaml
Type: String
Parameter Sets: (All)
Aliases: RunbookPath

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

### -Tags
Specifies one or more runbook tags.
You must provide all tags within one string, separated by commas.

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

[Get-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaRunbook.md)

[Edit-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Edit-SmaRunbook.md)

[Publish-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Publish-SmaRunbook.md)

[Remove-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaRunbook.md)

[Start-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Start-SmaRunbook.md)

