---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B811FF74-7FE4-4C0D-86B7-F6795947F52A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMRunAsAccount

## SYNOPSIS
Gets RunAs accounts.

## SYNTAX

### FromDomainUserName (Default)
```
Get-SCSMRunAsAccount [[-Domain] <String>] [[-UserName] <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDisplayName
```
Get-SCSMRunAsAccount [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMRunAsAccount [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCSMRunAsAccount [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMRunAsAccount** cmdlet retrieves RunAs accounts.
RunAs accounts contain the user credentials under which workflows run.
They make it possible for Service Manager to act on behalf of a specific user.
If the *Name* parameter, the *DisplayName* parameter, or the *Domain* parameter and the *UserName* parameter are omitted, all RunAs accounts are returned.
The *Name* or *DisplayName* parameters support wildcard matching.

## EXAMPLES

### Example 1: Get the RunAs account information from Service Manager
```
PS C:\>Get-SCSMRunAsAccount
Domain       UserName    DisplayName                                     Description

------       --------    -----------                                     -----------

NT Authority LocalSystem Workflow Account                                All workflows run under this account. It mu... 

                         Automatic Agent Management Account              This account will be used to automatically ... 

                         Reserved                                        This profile is reserved and must not be used. 

                         Default Action Account                          The default Health Service Action Account

                         Privileged Monitoring Account                   This profile is used for monitoring which c... 

                         Reserved                                        This profile is reserved and must not be used. 

                         Active Directory Based Agent Assignment Account Account used by AD based agent assignment m... 

                         Validate Alert Subscription Account             Account used by the validate alert subscrip... 

                         MPUpdate Action Account                         This account is used by the MPUpdate notifier

DOM          user     Test

NT Authority LocalSystem Operational Database Account                    This account is used to read and write info...
```

This command retrieves the RunAs account information from Service Manager.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

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
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.
The default value is the current user.

You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: User account of the current context
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the RunAs account profile name to retrieve.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain
Specifies the domain of the RunAs account to be retrieved.

```yaml
Type: String
Parameter Sets: FromDomainUserName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the *SecureReference* property of the **RunAsAccount** object.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the RunAs account to retrieve.

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default is the current management group connection.

Enter a **ManagementGroupConnection** object that is returned by the Get-SCManagementGroupConnection cmdlet.

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

### -UserName
Specifies the user name to use for the RunAs account.

```yaml
Type: String
Parameter Sets: FromDomainUserName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid
You can pipe a GUID of a **RunAsAccount** to the *Id* parameter of the **Get-SCSMRunAsAccount** cmdlet.

### System.String
You can pipe a name of a **RunAsAccount** to the *Name* parameter of the **Get-SCSMRunAsAccount** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Core.SdkUtilities.Security.UserAccount
The object that encapsulates the RunAs account name and the credentials that are associated with that RunAs account.

## NOTES

## RELATED LINKS

[New-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMRunAsAccount.md)

[Remove-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMRunAsAccount.md)

[Update-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMRunAsAccount.md)

