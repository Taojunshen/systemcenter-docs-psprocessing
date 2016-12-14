---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=306452
schema: 2.0.0
ms.assetid: 61AB8FE9-29C5-4028-A63C-01436CD94A64
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/v1/Get-SmaJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SmaJob

## SYNOPSIS
Gets a runbook job.

## SYNTAX

### GetAll (Default)
```
Get-SmaJob -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByJobId
```
Get-SmaJob [-Id <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByJobContextId
```
Get-SmaJob [-ContextId <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookId
```
Get-SmaJob [-RunbookId <String[]>] -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### ByRunbookName
```
Get-SmaJob [-RunbookName <String[]>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaJob** cmdlet gets one or more runbook jobs in Service Management Automation (SMA).
Specify the web service endpoint and, if necessary, a port.
By default, all jobs are returned.
To get a specific job, specify the *JobId*, *JobContext*, *RunbookId*, or *RunbookName* parameter.

## EXAMPLES

### Example 1: Get a runbook job
```
PS C:\> Get-SmaJob -WebServiceEndpoint "https://localhost" -JobId "2989b069-24fe-40b9-b3bd-cb7e5eac4b647"
```

This command gets the job with the Job ID named 2989b069-24fe-40b9-b3bd-cb7e5eac4b647.

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

### -ContextId
Specifies an array of context IDs.

```yaml
Type: String[]
Parameter Sets: ByJobContextId
Aliases: JobContextId

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
Specifies an array of job IDs.

```yaml
Type: String[]
Parameter Sets: ByJobId
Aliases: JobId

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

### -RunbookId
Specifies an array of IDs, as strings, of a runbook.

```yaml
Type: String[]
Parameter Sets: ByRunbookId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunbookName
Specifies an array of runbook names.

```yaml
Type: String[]
Parameter Sets: ByRunbookName
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

[Resume-SmaJob](xref:SystemCenter2016/ServiceManagementAutomation/v1/Resume-SmaJob.md)

[Stop-SmaJob](xref:SystemCenter2016/ServiceManagementAutomation/v1/Stop-SmaJob.md)

[Suspend-SmaJob](xref:SystemCenter2016/ServiceManagementAutomation/v1/Suspend-SmaJob.md)

