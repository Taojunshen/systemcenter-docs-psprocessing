---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=306453
schema: 2.0.0
ms.assetid: 37A4021A-9621-4796-93B8-8E0DD005212D
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaJobOutput.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaJobOutput.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/ServiceManagementAutomation/v1/Get-SmaJobOutput.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SmaJobOutput

## SYNOPSIS
Gets the output of a SMA job.

## SYNTAX

```
Get-SmaJobOutput -Id <String> [-StartTime <DateTime>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] -Stream <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SmaJobOutput** cmdlet gets the output of a Service Management Automation (SMA) job.
Specify an SMA job ID and the web service endpoint.

## EXAMPLES

### Example 1: Get the output of a Service Management Automation job
```
PS C:\> Get-SmaJobOutput -Id "2989b069-24fe-40b9-b3bd-cb7e5eac4b64" -WebServiceEndpoint "https://contoso.com/app01"
```

This command gets all of the output of the job with the specified GUID for the specified web service endpoint.

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
Specifies the job ID, as a string.

```yaml
Type: String
Parameter Sets: (All)
Aliases: JobId

Required: True
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

### -StartTime
Specifies a start time as a **DateTime** object.
The cmdlet gets output created after this time.
To get a **DateTime** object, use the Get-Date cmdlet.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stream
Specifies the type of output.
Valid values are:

-- Any
-Debug 
- Error
- Output
- Progress
- Verbose
- Warning

Note: Stream values are case-sensitive.
If the wrong case is used, the error "job id '\<GUID\>' not found" is returned.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OutputType
Accepted values: Any, Progress, Output, Warning, Error, Debug, Verbose

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SmaJob](xref:ServiceManagementAutomation/v1/Get-SmaJob.md)

