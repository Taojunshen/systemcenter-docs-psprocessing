---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E738D85F-063F-4453-A5B5-7A6AC30CABCA
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMChannel.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMChannel.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMChannel.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMChannel

## SYNOPSIS
Retrieves the email notification channels that are defined in Service Manager.

## SYNTAX

```
Get-SCSMChannel [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMChannel** cmdlet retrieves the email notification channels that are defined in Service Manager.
The object returned includes the retry interval in seconds, the return address of the email, the status of the channel, and the list of Simple Mail Transfer Protocol (SMTP) servers.

## EXAMPLES

### Example 1: Get settings for the notifications channel
```
PS C:\>Get-SCSMChannel
DisplayName          : E-Mail Notification Channel
IsEnabled            : False
RetryIntervalSeconds : 30
ReturnAddress        : pfuller@Consoto.com
```

This command retrieves the settings for the email Notification channel.

### Example 2: Get servers for the email notification channel
```
PS C:\>$EmailChannel = Get-SCSMChannel
PS C:\> $EmailChannel.ConfigurationSources | Format-Table -AtuoSize
SequenceNumber Server        PortNumber Authentication
-------------- ------        ---------- --------------
0              SMTPServer1   25          WindowsIntegrated
1              SMTPServer2   25          WindowsIntegrated
2              SMTPServer3   25          WindowsIntegrated
```

The first command retrieves the settings for the email notification channel, and then stores them in the $EmailChannel variable.

The second command uses standard dot syntax to display the ConfigruationSources property of $EmailChannel.
The command uses **Format-Table** to format the results.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

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

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

```yaml
Type: Connection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.NotificationChannel.SMTP.Projection
The output of this cmdlet is the **SCSMChannel** object that contains the SMTP settings for the email notification channel.

## NOTES

## RELATED LINKS

[Set-SCSMChannel](xref:SystemCenter2016/ServiceManager/vlatest/Set-SCSMChannel.md)

