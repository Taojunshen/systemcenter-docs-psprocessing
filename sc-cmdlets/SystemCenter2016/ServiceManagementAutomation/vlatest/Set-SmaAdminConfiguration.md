---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CB9C632F-254F-4018-8321-DC696D66A244
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaAdminConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaAdminConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaAdminConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SmaAdminConfiguration

## SYNOPSIS
Modifies administrative configuration settings in SMA.

## SYNTAX

```
Set-SmaAdminConfiguration [-Telemetry <Boolean>] [-DrainTimeInSeconds <Int32>]
 [-ScriptExecutionPolicy <String>] [-MaxJobRecords <Int32>] [-PurgeJobsOlderThanCountDays <Int32>] [-Force]
 [-ChartTimeSliceSampleSize <ChartTimeSliceSampleSize>] -WebServiceEndpoint <String> [-Port <Int32>]
 [-AuthenticationType <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SmaAdminConfiguration** cmdlet modifies administration configuration settings in Service Management Automation (SMA).
Specify the web service endpoint and, if necessary, a port.

Use this cmdlet to configure the following settings: 

- Whether to share diagnostic and usage data with Microsoft
- Drain time
- Script execution policy
- Chart time slice sample size
- The maximum job records to store before purging the oldest jobs
- The maximum age of a job before it is purged

## EXAMPLES

### Example 1: Modify an administrative configuration setting
```
PS C:\> Set-SmaAdminConfiguration -WebServiceEndpoint "https://contoso.com/app01" -DrainTimeInSeconds 60
```

This command sets the drain time to 60 seconds.

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

### -ChartTimeSliceSampleSize
Specifies the chart time slice sample size.
Valid values are:

- Small
- Medium
- Large
- ExtraLarge

```yaml
Type: ChartTimeSliceSampleSize
Parameter Sets: (All)
Aliases: 
Accepted values: Small, Medium, Large, ExtraLarge

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

### -DrainTimeInSeconds
Specifies the time, in seconds, after which the runbook worker hosts terminate running jobs after a runbook worker service stop has been initiated.
While the host is draining, existing jobs are given the specified drain time seconds to suspend or terminate naturally, and no new jobs are accepted.

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

### -MaxJobRecords
Specifies the maximum number of job records that are retained.

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

### -PurgeJobsOlderThanCountDays
Specifies the number of days job history is kept.
Jobs older than this value are purged.

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

### -ScriptExecutionPolicy
Determines the Windows PowerShell execution policy for runbook jobs on the worker hosts.
For information about execution policies, type `Get-Help about_Execution_Policies`.
Valid values for this parameter are: 

- Restricted.
You cannot run scripts.
You can use Windows PowerShell only in interactive mode.
- AllSigned.
You can run only scripts signed by a trusted publisher.
- RemoteSigned.
Downloaded scripts must be signed by a trusted publisher before you can run the scripts.
- Unrestricted.
No restrictions; you can run all Windows PowerShell scripts.

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

### -Telemetry
Indicates whether to share diagnostic and usage data with Microsoft.
The acceptable values for this parameter are:

- $True.
Share diagnostic and usage data with Microsoft. 
- $False.
Do not share diagnostic and usage data with Microsoft.

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

[Get-SmaAdminConfiguration](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Get-SmaAdminConfiguration.md)

