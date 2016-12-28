---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C4ABC0B4-5D46-4ABF-8C55-ACE34BE3EF88
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Set-SCSMChannel.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Set-SCSMChannel.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Set-SCSMChannel.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSMChannel

## SYNOPSIS
Sets the properties of the email notification channel in Service Manager.

## SYNTAX

```
Set-SCSMChannel [-Enable <Boolean>] [-RetryInterval <Int32>] [-ReturnAddress <String>]
 [-SMTPServerList <Hashtable[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSMChannel** cmdlet sets the properties of the email notification channel in Service Manager.
This cmdlet configures and enables email notifications that Service Manager sends to an SMTP server.
Notification channels are the method by which Service Manager sends notification messages to users.

## EXAMPLES

### Example 1: Change the reply address of the channel
```
PS C:\>Set-SCSMChannel -ReturnAddress "Administrator@Woodgrove.com"
```

This command changes the **replyTo** address property of the email channel.

### Example 2: Set the servers for the channel
```
PS C:\>Set-SCSMChannel -SMTPServerList @{ Server = "SMTPServer1"; Port = 25; Authentication = "Windows" },
    @{ Server = "SMTPServer2"; Port = 25; Authentication = "Windows" },
    @{ Server = "SMTPServer3"; Port = 25; Authentication = "Windows" }
```

This command sets the list of SMTP servers for the email channel.

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

### -Enable
Indicates whether this cmdlet enables or disables the channel.

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

### -RetryInterval
Specifies how many seconds to wait before retrying to send email.

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

### -ReturnAddress
Specifies the return address when it sends an email notification.

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

### -SCSession
Specifies the object that represents the session to a Service Manager management server.

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

### -SMTPServerList
Specifies the list of SMTP servers that Service Manager uses to send email notifications.
Service Manager uses the servers in the order in which they are listed.
The list is an array of hash tables with the following allowed keys: 

- Server.
The SMTP server to use.
You must specify this key. 
- Port.
The SMTP port to use.
The default value is port 25. 
- Authentication.
Valid values are Windows and Anonymous.
The default value is Anonymous.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMChannel](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMChannel.md)

