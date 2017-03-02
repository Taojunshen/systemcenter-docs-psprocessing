---
external help file: Microsoft.SystemCenter.ServiceManagementAutomation.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0D1DEB99-0D41-4038-84C9-29C6BC74369B
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Start-SmaRunbook.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Start-SmaRunbook.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagementAutomation/vlatest/Start-SmaRunbook.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-SmaRunbook

## SYNOPSIS
Starts a runbook job.

## SYNTAX

### ByRunbookName (Default)
```
Start-SmaRunbook [-Name <String>] [-Parameters <IDictionary>] [-ScheduleName <String>]
 -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByRunbookId
```
Start-SmaRunbook [-Id <String>] [-Parameters <IDictionary>] [-ScheduleName <String>]
 -WebServiceEndpoint <String> [-Port <Int32>] [-AuthenticationType <String>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SmaRunbook** cmdlet starts a runbook job.
Specify the ID or name of a runbook and the web service endpoint.
If necessary, specify the port of the Service Management Automation (SMA) web service.

## EXAMPLES

### Example 1: Start a runbook job
```
PS C:\> Start-SmaRunbook -WebServiceEndpoint https://localhost -Name "Runbk01" -Parameters @{"StringParam"="Value"; "IntParam"=2}
```

This command starts the runbook named Runbk01, specifying the parameters for the runbook job.

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

### -Parameters
Specifies a hash table of key and value pairs.
The keys in the hash table are the runbook parameter names.
The values in the hash table are the runbook parameter values.

```yaml
Type: IDictionary
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

### -ScheduleName
Specifies the name of a job schedule on which to start the runbook.
To create a schedule in SMA, use the Set-SmaSchedule cmdlet.

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

[Import-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Import-SmaRunbook.md)

[Publish-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Publish-SmaRunbook.md)

[Remove-SmaRunbook](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Remove-SmaRunbook.md)

[Set-SmaSchedule](xref:SystemCenter2016/ServiceManagementAutomation/vlatest/Set-SmaSchedule.md)

