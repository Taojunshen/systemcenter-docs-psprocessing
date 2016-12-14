---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239460
schema: 2.0.0
ms.assetid: FD1A5D21-18BD-4EFE-B253-EC176A63704C
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Add-SCOMNotificationChannel.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Add-SCOMNotificationChannel.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Add-SCOMNotificationChannel.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOMNotificationChannel

## SYNOPSIS
Adds a notification channel in Operations Manager.

## SYNTAX

### UsingSMTP (Default)
```
Add-SCOMNotificationChannel [-Name] <String> [-Port <UInt32>] [-DisplayName <String>] [-Description <String>]
 -Server <String> [-From] <String> [-ReplyTo <String>] [-Header <Hashtable>] [-Anonymous] [-ExternalEmail]
 [-ExternalEmailRunasProfile <String>] [-BackupSmtpServer <String[]>] [-MaxPrimaryRecipientsPerMail <Int32>]
 [-PrimaryRetryInterval <TimeSpan>] [-Subject <String>] -Body <String> [-BodyAsHtml] [-Encoding <String>]
 [-NoSubjectEncoding] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UsingSIP
```
Add-SCOMNotificationChannel [-Name] <String> [-Port <UInt32>] [-DisplayName <String>] [-Description <String>]
 [-UserName] <Uri> [-ContentType <String>] -Server <String> [-SipProtocol <SipTransportProtocol>]
 [-SipAuthentication <SipNotificationAuthenticationProtocols>] [-PreferredUserName <String>] -Body <String>
 [-Encoding <String>] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CommandAction
```
Add-SCOMNotificationChannel [-Name] <String> [-DisplayName <String>] [-Description <String>]
 [-ApplicationPath] <String> [[-Argument] <String>] [-WorkingDirectory <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UsingSMS
```
Add-SCOMNotificationChannel [-Name] <String> [-DisplayName <String>] [-Description <String>]
 [-PrimaryRetryInterval <TimeSpan>] [-DeviceEnumerationInterval <TimeSpan>] [-Sms] [[-Device] <String>]
 [[-BackupDevice] <String[]>] -Body <String> [-Encoding <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMNotificationChannel** cmdlet adds a notification channel in System Center 2016 - Operations Manager.
Notification channels inform administrators of an alert, or they run automation in response to an alert.
A notification channel uses a delivery mechanism in Operations Manager, such as email, instant messaging (IM), Short Message Service (SMS), or command, to deliver notifications.

## EXAMPLES

### Example 1: Add a notification channel
```
PS C:\>$Subject = "SCOM alert `$Data[Default='Not Present']/Context/DataItem/AlertName`$"
PS C:\> $Body = "Owner is `$Data[Default='Not Present']/Context/DataItem/AlertOwner`$"
PS C:\> Add-SCOMNotificationChannel -Name "Contoso.Email" -Server "mail.contoso.com" -From "scom@contoso.net" -Subject $Subject -Body $Body
```

This example adds a standard SMTP email channel.

The first command stores the subject line in the variable named $Subject.

The second command stores the message body in the variable named $Body.

The third command uses the **Add-SCOMNotificationChannel** cmdlet to add an SMTP email channel.

### Example 2: Add a notification channel for IM
```
PS C:\>$Body = "SCOM alert `$Data[Default='Not Present']/Context/DataItem/AlertName`$"
PS C:\> Add-SCOMNotificationChannel -Name "Contoso.IM" -Server "sipserver.contoso.com" -UserName 'sip:scomadmin' -Body $Body
```

This example adds an IM channel that has a return address of scomadmin.

The first command stores the message body in the variable named $Body.

The second command uses the **Add-SCOMNotificationChannel** cmdlet to add an IM channel.

### Example 3: Add a notification channel for SMS
```
PS C:\>$Body = "SCOM alert `$Data[Default='Not Present']/Context/DataItem/AlertName`$"
PS C:\> Add-SCOMNotificationChannel -Sms -Name "Contoso.SMS" -Body $Body -Encoding "Unicode"
```

This example adds an SMS channel that has Unicode encoding.

The first command stores the message body in the variable named $Body.

The second command uses the **Add-SCOMNotificationChannel** cmdlet to add an SMS channel.

### Example 4: Add a command notification channel
```
PS C:\>$Path = "C:\OnNotify.exe"
PS C:\> $Arg = "/notify /owner `"`$Data[Default='Not Present']/Context/DataItem/AlertOwner`$`""
PS C:\> $WorkingDir = "C:\"
PS C:\> Add-SCOMNotificationChannel -Name "Contoso.Command" -ApplicationPath $Path -Argument $Arg -WorkingDirectory $WorkingDir
```

This example adds a command notification channel that runs the OnNotify.exe program.

The first command stores the path to the executable file in the variable named $Path.

The second command stores the arguments in the variable named $Arg.

The third command stores the working directory in the variable named $WorkingDir.

The fourth command uses the **Add-SCOMNotificationChannel** cmdlet to add a command notification channel.

## PARAMETERS

### -Anonymous
Indicates that an anonymous Simple Mail Transfer Protocol (SMTP) server sends email notifications.

```yaml
Type: SwitchParameter
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ApplicationPath
Specifies the application path of a command channel.

```yaml
Type: String
Parameter Sets: CommandAction
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Argument
Specifies an argument list to a command channel.

```yaml
Type: String
Parameter Sets: CommandAction
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackupDevice
Specifies an array of secondary SMS devices.

```yaml
Type: String[]
Parameter Sets: UsingSMS
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BackupSmtpServer
Specifies an array of backup SMTP servers.
Backup servers use the same configuration as the primary SMTP server.

```yaml
Type: String[]
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Body
Specifies the body of a notification message.

```yaml
Type: String
Parameter Sets: UsingSMTP, UsingSIP, UsingSMS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -BodyAsHtml
Indicates that the service formats the body of the message as HTML.

```yaml
Type: SwitchParameter
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name,  localhost, or a dot (.).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContentType
Specifies the content type of an IM.
By default, the content type is `text/plain`.

```yaml
Type: String
Parameter Sets: UsingSIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type "`Get-Help Get-Credential`".

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

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
Specifies a description for a notification channel.
If you do not set a value, the default is the value of the *DisplayName* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Device
Specifies a primary SMS device.

```yaml
Type: String
Parameter Sets: UsingSMS
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeviceEnumerationInterval
Specifies a time interval between SMS notifications.
By default, the notification channel waits 10 seconds.

```yaml
Type: TimeSpan
Parameter Sets: UsingSMS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies a display name for a notification channel.
If you do not set a value, the default is the value of the *Name* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Encoding
Specifies the encoding format for a notification message.
An SMTP channel uses UTF-8 encoding by default.
An IM channel also uses UTF-8 encoding by default.
An SMS channel uses Default encoding by default but can alternately use Unicode encoding.

```yaml
Type: String
Parameter Sets: UsingSMTP, UsingSIP, UsingSMS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -From
Specifies the From header in a notification e-mail message.

```yaml
Type: String
Parameter Sets: UsingSMTP
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Header
Specifies headers, as key-value pairs, in a notification email message.

```yaml
Type: Hashtable
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxPrimaryRecipientsPerMail
Specifies the maximum number of recipients for a notification email message.

```yaml
Type: Int32
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of a notification channel.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoSubjectEncoding
Indicates that the cmdlet does not encode the email subject line.

```yaml
Type: SwitchParameter
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Specifies the port number for a channel.

An SMTP channel uses port 25 by default.
An IM channel that uses TCP uses port 5060 by default, and an IM channel that uses Transport Layer Security (TLS) uses port 5061 by default.

```yaml
Type: UInt32
Parameter Sets: UsingSMTP, UsingSIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PreferredUserName
Specifies the preferred user name of an IM channel.
If you do not set a value, the default is the value of the *Username* parameter.

```yaml
Type: String
Parameter Sets: UsingSIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrimaryRetryInterval
Specifies a retry interval.
The service attempts to switch back to the primary SMTP server or SMS device.
By default, the interval is five minutes.

```yaml
Type: TimeSpan
Parameter Sets: UsingSMTP, UsingSMS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ReplyTo
Specifies the Reply-to header in a notification email message.

```yaml
Type: String
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

Enter a connection object for a management group, such as one that the **Get-SCManagementGroupConnection** cmdlet returns.

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

### -Server
Specifies a server that provides SMTP and IM channels for notifications.

```yaml
Type: String
Parameter Sets: UsingSMTP, UsingSIP
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SipAuthentication
Specifies a Session Initiation Protocol (SIP) authentication mechanism (NTLM or Kerberos) for IM channels.
By default, SIP authentication uses NTLM authentication.

```yaml
Type: SipNotificationAuthenticationProtocols
Parameter Sets: UsingSIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SipProtocol
Specifies a SIP transport protocol (TCP or TLS) for IM channels.
By default, SIP uses TCP as a transport protocol.

```yaml
Type: SipTransportProtocol
Parameter Sets: UsingSIP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sms
Indicates that the cmdlet sends notifications by using SMS.

```yaml
Type: SwitchParameter
Parameter Sets: UsingSMS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Subject
Specifies a subject line for the notification email message.

```yaml
Type: String
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies a return address for IM.

```yaml
Type: Uri
Parameter Sets: UsingSIP
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkingDirectory
Specifies a working directory for a command channel.
By default, a command channel uses the %systemdrive% as a working directory.

```yaml
Type: String
Parameter Sets: CommandAction
Aliases: 

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

### -ExternalEmail
Specifies whether to use external email.

```yaml
Type: SwitchParameter
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExternalEmailRunasProfile
Specifies the Run as profile for external email.

```yaml
Type: String
Parameter Sets: UsingSMTP
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-SCOMNotificationChannel](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMNotificationChannel.md)

[Remove-SCOMNotificationChannel](xref:SystemCenter2016/OperationsManager/v1/Remove-SCOMNotificationChannel.md)

