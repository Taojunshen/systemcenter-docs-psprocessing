---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=306445
schema: 2.0.0
ms.assetid: 0C2AB0DE-4644-4768-B088-3DC7FED38359
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Edit-SmaRunbook.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Edit-SmaRunbook.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceManagementAutomation/v1/Edit-SmaRunbook.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Edit-SmaRunbook

## SYNOPSIS
Updates the draft field of a runbook.

## SYNTAX

### ByRunbookName (Default)
```
Edit-SmaRunbook [-Name <String>] -Path <String> [-Overwrite] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRunbookId
```
Edit-SmaRunbook [-Id <String>] -Path <String> [-Overwrite] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Edit-SmaRunbook** updates the draft field of a runbook.
Provide a Windows PowerShell script (.ps1) file that contains a runbook which becomes the draft runbook.
If a draft already exists, use the *Overwrite* parameter to force the cmdlet to overwrite the existing draft.

To edit a specific type of runbook (Windows PowerShell script or workflow), you must create a new runbook of that type.

## EXAMPLES

### Example 1: Overwrite an existing draft runbook
```
PS C:\> Edit-SmaRunbook -Name "Runbk01" -WebServiceEndpoint "https://contoso.com" -Path "App01.ps1" -Overwrite
```

This command overwrites the existing draft runbook.

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

### -Id
Specifies the ID of a runbook.

```yaml
Type: String
Parameter Sets: ByRunbookId
Aliases: RunbookId

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a runbook.

```yaml
Type: String
Parameter Sets: ByRunbookName
Aliases: RunbookName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Overwrite
Indicates that the new draft runbook overwrites the existing draft, if one exists.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies a path to the new draft runbook.

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

[Get-SmaRunbook](xref:ServiceManagementAutomation/v1/Get-SmaRunbook.md)

[Import-SmaRunbook](xref:ServiceManagementAutomation/v1/Import-SmaRunbook.md)

[Publish-SmaRunbook](xref:ServiceManagementAutomation/v1/Publish-SmaRunbook.md)

[Remove-SmaRunbook](xref:ServiceManagementAutomation/v1/Remove-SmaRunbook.md)

[Start-SmaRunbook](xref:ServiceManagementAutomation/v1/Start-SmaRunbook.md)

