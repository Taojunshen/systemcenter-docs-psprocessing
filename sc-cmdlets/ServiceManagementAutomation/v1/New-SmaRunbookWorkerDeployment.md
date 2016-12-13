---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=306462
schema: 2.0.0
ms.assetid: 1C0AA81C-0D8D-4B52-AEBB-1C07631331B0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/New-SmaRunbookWorkerDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/New-SmaRunbookWorkerDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceManagementAutomation/v1/New-SmaRunbookWorkerDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SmaRunbookWorkerDeployment

## SYNOPSIS
Changes the runbook worker deployment in SMA.

## SYNTAX

### ByComputerName (Default)
```
New-SmaRunbookWorkerDeployment [-ComputerName] <String[]> [-Force] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRunbookWorkers
```
New-SmaRunbookWorkerDeployment -RunbookWorkers <SmaRunbookWorkerDeploymentInfo[]> [-Force]
 -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SmaRunbookWorkerDeployment** cmdlet changes the runbook worker deployment in Service Management Automation (SMA).
Runbook workers are processes configured to pick up and process runbook jobs.

## EXAMPLES

### Example 1: Create runbook workers
```
PS C:\> New-SmaRunbookWorkerDeployment -WebServiceEndpoint "https://contoso.com/app01" -ComputerName "RWComputer01", "RWComputer02"
```

This command creates a runbook worker deployment that contains the computers named RWcomputer01 and RWComputer02 for the specified web service endpoint.

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

### -ComputerName
Specifies an array of names for computers that host runbooks.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
If you do not specify this parameter, the cmdlet uses the local computer.

```yaml
Type: String[]
Parameter Sets: ByComputerName
Aliases: 

Required: True
Position: 1
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

### -Force
Forces the command to run without asking for user confirmation.

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

### -RunbookWorkers
Specifies the runbook workers to include in the new deployment.

```yaml
Type: SmaRunbookWorkerDeploymentInfo[]
Parameter Sets: ByRunbookWorkers
Aliases: 

Required: True
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

[about_SMA_Runbook_Worker_Deployment](http://go.microsoft.com/fwlink/?LinkId=301478)

[Get-SmaRunbookWorkerDeployment](xref:ServiceManagementAutomation/v1/Get-SmaRunbookWorkerDeployment.md)

