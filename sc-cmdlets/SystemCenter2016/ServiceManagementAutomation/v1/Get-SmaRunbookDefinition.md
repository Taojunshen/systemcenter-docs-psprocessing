---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=323487
schema: 2.0.0
ms.assetid: 83A41AC8-ECC6-49CB-AEB6-3A06955F2847
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaRunbookDefinition.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaRunbookDefinition.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaRunbookDefinition.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SmaRunbookDefinition

## SYNOPSIS
Gets a runbook definition.

## SYNTAX

### All (Default)
```
Get-SmaRunbookDefinition -Type <RunbookVersionType> -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookId
```
Get-SmaRunbookDefinition -Id <String[]> -Type <RunbookVersionType> -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookName
```
Get-SmaRunbookDefinition [-Name] <String[]> -Type <RunbookVersionType> -WebServiceEndpoint <String>
 [-Port <Int32>] [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ByVersionId
```
Get-SmaRunbookDefinition -VersionId <String[]> -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaRunbookDefinition** cmdlet gets one or more runbooks.
By default, all runbook definitions of the specified version type are returned.
To get a specific runbook, specify its name or ID.

## EXAMPLES

### Example 1: Get a runbook definition by name
```
PS C:\>Get-SmaRunbookDefinition -WebServiceEndpoint "https://localhost" -Name "RunbookDef01" -Type "Draft"
```

This command gets the draft runbook definition of the runbook with the name RunbookDef01.

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
Specifies an array of runbook IDs that this cmdlet gets runbook definitions from.

```yaml
Type: String[]
Parameter Sets: ByRunbookId
Aliases: RunbookId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of runbook names that this cmdlet gets runbook definitions from.

```yaml
Type: String[]
Parameter Sets: ByRunbookName
Aliases: RunbookName

Required: True
Position: 0
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

### -Type
Specifies a runbook version type.
Valid values are: 

- Published
- Draft

```yaml
Type: RunbookVersionType
Parameter Sets: All, ByRunbookId, ByRunbookName
Aliases: 
Accepted values: Published, Draft

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VersionId
Specifies an array of runbook version IDs.

```yaml
Type: String[]
Parameter Sets: ByVersionId
Aliases: 

Required: True
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

[Get-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaRunbook.md)

