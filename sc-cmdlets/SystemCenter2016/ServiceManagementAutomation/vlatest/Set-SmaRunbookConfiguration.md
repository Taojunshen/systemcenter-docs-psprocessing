---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=323486
schema: 2.0.0
ms.assetid: F0510D9D-09EE-4D63-86FC-A8A43257B784
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaRunbookConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaRunbookConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaRunbookConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SmaRunbookConfiguration

## SYNOPSIS
Modifies the configuration of a runbook.

## SYNTAX

### All (Default)
```
Set-SmaRunbookConfiguration [-LogDebug <Boolean>] [-LogVerbose <Boolean>] [-LogProgress <Boolean>]
 [-Description <String>] [-RunbookWorker <String>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookId
```
Set-SmaRunbookConfiguration -Id <String> [-LogDebug <Boolean>] [-LogVerbose <Boolean>] [-LogProgress <Boolean>]
 [-Description <String>] [-RunbookWorker <String>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookName
```
Set-SmaRunbookConfiguration -Name <String> [-LogDebug <Boolean>] [-LogVerbose <Boolean>]
 [-LogProgress <Boolean>] [-Description <String>] [-RunbookWorker <String>] -WebServiceEndpoint <String>
 [-Port <Int32>] [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmaRunbookConfiguration** cmdlet modifies the configuration of a runbook.

## EXAMPLES

### Example 1: Update a runbook configuration
```
PS C:\>Set-SmaRunbookConfiguration -Name "Runbook01" -WebServiceEndpoint "https://localhost" -Description "First runbook" -LogDebug $True -LogProgress $True -LogVerbose $True
```

This command adds a description to the runbook named Runbook01 and enables all logging options.

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
Specifies a **PSCredential** object for the connection to the Service Management Automation (SMA) web service.
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

### -Description
Provides a description for a runbook.

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

### -Id
Specifies the ID of a runbook.

```yaml
Type: String
Parameter Sets: ByRunbookId
Aliases: RunbookId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogDebug
Indicates whether this cmdlet logs debug output.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogProgress
Indicates whether this cmdlet logs progress output.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogVerbose
Indicates whether this cmdlet logs verbose output.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a runbook.

```yaml
Type: String
Parameter Sets: ByRunbookName
Aliases: RunbookName

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

### -RunbookWorker
Specifies a designated runbook worker for the runbook.
You can specify an existing runbook worker in the current SMA deployment.
Use the Get-SmaRunbookWorkerDeployment cmdlet to get a list of runbook workers in the current SMA deployment.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaRunbook.md)

