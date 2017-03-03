---
external help file: OperationsManager-help.xml
online version: 
schema: 2.0.0
ms.assetid: 60FF0DA1-F641-4C9F-BA59-313BC4BFEF02
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMRunAsAccount

## SYNOPSIS
Adds a Run As account to a management group.

## SYNTAX

### Windows (Default)
```
Add-SCOMRunAsAccount [-Windows] [-Name] <String> [-Description <String>] [-RunAsCredential] <PSCredential>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### CommunityString
```
Add-SCOMRunAsAccount [-CommunityString] [-Name] <String> [-Description <String>] [-String] <SecureString>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Basic
```
Add-SCOMRunAsAccount [-Basic] [-Name] <String> [-Description <String>] [-RunAsCredential] <PSCredential>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Digest
```
Add-SCOMRunAsAccount [-Digest] [-Name] <String> [-Description <String>] [-RunAsCredential] <PSCredential>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Simple
```
Add-SCOMRunAsAccount [-Simple] [-Name] <String> [-Description <String>] [-RunAsCredential] <PSCredential>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ActionAccount
```
Add-SCOMRunAsAccount [-ActionAccount] [-Name] <String> [-Description <String>]
 [-RunAsCredential] <PSCredential> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Binary
```
Add-SCOMRunAsAccount [-Binary] [-Name] <String> [-Description <String>] [-Path] <String>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SnmpV3
```
Add-SCOMRunAsAccount [-SnmpV3] [-Name] <String> [-Description <String>] [-UserName] <String>
 [-AuthProtocolAndKey <PSCredential>] [-PrivacyProtocolAndKey <PSCredential>] [-Context <String>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SCXMonitoring
```
Add-SCOMRunAsAccount [-SCXMonitoring] [-Name] <String> [-Description <String>]
 [-RunAsCredential] <PSCredential> [-Sudo] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceUserPassNoPrivSu
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>]
 [-RunAsCredential] <PSCredential> [-Su] -SuPassword <SecureString> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceUserPassNoPrivSudo
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>]
 [-RunAsCredential] <PSCredential> [-Sudo] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceUserPassPriv
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>]
 [-RunAsCredential] <PSCredential> [-Privileged] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceSSHKeyNoPrivSu
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>] [-Path] <String>
 [-UserName] <String> [-Passphrase <SecureString>] [-Su] -SuPassword <SecureString> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceSSHKeyNoPrivSudo
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>] [-Path] <String>
 [-UserName] <String> [-Passphrase <SecureString>] [-Sudo] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SCXMaintenanceSSHKeyPriv
```
Add-SCOMRunAsAccount [-SCXMaintenance] [-Name] <String> [-Description <String>] [-Path] <String>
 [-UserName] <String> [-Passphrase <SecureString>] [-Privileged] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMRunAsAccount** cmdlet adds a Run As account to a management group.
A Run As account enables users to specify the necessary permissions for use with rules, tasks, monitors, and discoveries targeted to specific computers on an as-needed basis.

System Center 2016 - Operations Manager distributes the Run As account credentials to either all agent-managed computers (the less secure option) or only to computers that you specify (the more secure option).
By default, all new accounts have the more secure distribution option.
To modify the account distribution policy, use the **Set-SCOMRunAsDistribution** cmdlet.

## EXAMPLES

### Example 1: Add a Windows Run As account
```
PS C:\>Add-SCOMRunAsAccount -Windows -Name "Contoso.Windows -Description "Account used for monitoring the Contoso domain" -RunAsCredential (Get-Credential)
```

This command adds a Run As account that uses Windows authentication.

### Example 2: Add a Community String Run As account
```
PS C:\>$CommunityString = Read-Host -AsSecureString
PS C:\> Add-SCOMRunAsAccount -CommunityString -Name "Contoso.CommStr" -String $CommunityString
```

This example adds a Run As account that uses Community String authentication.

The first command prompts the user to enter the community string for the account and stores the input as a secure string in the variable named $CommunityString.

The second account creates the account and specifies the string stored in $CommunityString as the community string for the account.

### Example 3: Add a Basic Authentication Run As account
```
PS C:\>Add-SCOMRunAsAccount -Basic -Name "Contoso.Basic" -RunAsCredential (Get-Credential)
```

This command adds a Run As account that uses basic web authentication.

### Example 4: Add a Simple Authentication Run As account
```
PS C:\>Add-SCOMRunAsAccount -Simple -Name "Contoso.Simple" -RunAsCredential (Get-Credential)
```

This command adds a Run As account that uses simple authentication.

### Example 5: Add a Digest Authentication Run As account
```
PS C:\>Add-SCOMRunAsAccount -Digest -Name "Contoso.Digest" -RunAsCredential (Get-Credential)
```

This command adds a Run As account that uses standard digest web authentication.

### Example 6: Add a Binary Authentication Run As account
```
PS C:\>Add-SCOMRunAsAccount -Binary -Name "Contoso.Binary" -Path "C:\accountfile.bin"
```

This command adds a Run As account that uses binary authentication.

### Example 7: Add an action account
```
PS C:\>Add-SCOMRunAsAccount -ActionAccount -Name "Contoso.Action" -RunAsCredential (Get-Credential)
```

This command adds an action account.

### Example 8: Add an SNMP version 3 account without context, authentication, or privacy
```
PS C:\>Add-SCOMRunAsAccount -Snmpv3 -Name "Contoso.Snmp1" -UserName "snmpuser"
```

This command adds an SNMP version 3 account that has no context, authentication protocol, or privacy protocol.

### Example 9: Add an SNMP version 3 account with context, authentication, and privacy
```
PS C:\>$Auth = Get-Credential
PS C:\>$Privacy = Get-Credential
PS C:\>Add-SCOMRunAsAccount -Snmpv3 -Name "Contoso.Snmp2" -UserName "snmpuser" -Context "snmp context" -AuthProtocolAndKey $Auth -PrivacyProtocolAndKey $Privacy
```

This example adds an SNMP version 3 account that specifies context, authentication protocol, and privacy protocol.

The first command gets the SNMP version 3 privacy protocol and key for the account and assigns them to the variable named $Auth.

The second command gets the SNMP version 3 privacy protocol and key for the account and assigns them to the variable named $Privacy.

The third command creates the account, uses the credentials stored in $Auth for the authoring protocol and key, and uses the credentials stored in $Privacy for the privacy protocol and key.

### Example 10: Add an SCX monitoring account with sudo elevation
```
PS C:\>Add-SCOMRunAsAccount -SCXMonitoring -Name "Contoso.SCXMon" -RunAsCredential (Get-Credential) -Sudo
```

This command adds an SCX monitoring account that uses sudo elevation.

### Example 11: Add an SCX maintenance account with privileged access
```
PS C:\>$Passphrase = Read-Host -AsSecureString
PS C:\> Add-SCOMRunAsAccount -SCXMaintenance -Name "Contoso.SCXMainSSH" -UserName "scxuser" -Path "C:\sshkey.ppk" -Passphrase $Passphrase -Privileged
```

This example adds an SCX maintenance account that has privileged access and uses a passphrase-protected SSH key.

The first command prompts the user to enter the passphrase and stores the passphrase as a secure string in the variable named $Passphrase.

The second command creates the account by using the passphrase stored in $Passphrase.

### Example 12: Add an SCX maintenance account without privileged access that uses sudo elevation
```
PS C:\>Add-SCOMRunAsAccount -SCXMaintenance -Name "Contoso.SCXMainUserName" -RunAsCredential (Get-Credential) -Sudo
```

This command adds an SCX maintenance account that does not have privileged access by specifying a user name and password and sudo elevation.

### Example 13: Add an SCX maintenance account that uses superuser elevation
```
PS C:\>$SuPassword = Read-Host -AsSecureString
PS C:\> Add-SCOMRunAsAccount -SCXMaintenance -Name "Contoso.SCXMainUserName" -RunAsCredential (Get-Credential) -Su -SuPassword $SuPassword
```

This example adds an SCX maintenance account that does not have privileged access by specifying a user name and password and a superuser account for elevation.

The first command prompts the user to enter the password, converts the user input to a secure string, and stores the password in the $SuPassword variable.

The second command creates the account by specifying the password that is stored in $SuPassword as the superuser password.

## PARAMETERS

### -ActionAccount
Indicates that the account is an action account.
An action account specifies credentials that the MonitoringHost management process uses to perform monitoring activities.

```yaml
Type: SwitchParameter
Parameter Sets: ActionAccount
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AuthProtocolAndKey
Specifies a **PSCredential** object that includes the Simple Network Management Protocol (SNMP) authentication protocol and key.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.

If this parameter appears, the cmdlet must also specify the *UserName* and *Passphrase* parameters.
Specify the protocol name MD5 or SHA for the *Username* parameter and the key for the *Passphrase* parameter.

```yaml
Type: PSCredential
Parameter Sets: SnmpV3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Basic
Indicates that the Run As account is a Basic Authentication account, which uses basic web authentication.

```yaml
Type: SwitchParameter
Parameter Sets: Basic
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Binary
Indicates that the Run As account is a Binary Authentication account, which uses authentication that the user defines.

```yaml
Type: SwitchParameter
Parameter Sets: Binary
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CommunityString
Indicates that the Run As account is a Community String account, which uses community string authentication in Simple Network Management Protocol (SNMP) version 2.

```yaml
Type: SwitchParameter
Parameter Sets: CommunityString
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
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be started on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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

### -Context
Specifies the SNMP version 3 context.

```yaml
Type: String
Parameter Sets: SnmpV3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about credential objects, type `Get-Help Get-Credential`.

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
Specifies the account description.
If this parameter does not appear, the default is the display name.

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

### -Digest
Indicates that the Run As account is a Digest Authentication account, which uses standard digest web authentication.

```yaml
Type: SwitchParameter
Parameter Sets: Digest
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the account name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: DisplayName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Passphrase
Specifies the Secure Shell (SSH) key passphrase for cross-platform maintenance accounts.

```yaml
Type: SecureString
Parameter Sets: SCXMaintenanceSSHKeyNoPrivSu, SCXMaintenanceSSHKeyNoPrivSudo, SCXMaintenanceSSHKeyPriv
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Specifies the path to the binary data file or SSH key.

```yaml
Type: String
Parameter Sets: Binary, SCXMaintenanceSSHKeyNoPrivSu, SCXMaintenanceSSHKeyNoPrivSudo, SCXMaintenanceSSHKeyPriv
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivacyProtocolAndKey
Specifies a **PSCredential** object that stores the SNMP privacy protocol and key.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.

If you specify this parameter appears, you must also specify the *UserName* and *Passphrase* parameters.
Specify the protocol name AES or DES for the *Username* parameter, and the key for the *Passphrase* parameter.

```yaml
Type: PSCredential
Parameter Sets: SnmpV3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Privileged
Indicates that the cross-platform maintenance account has privileged access.

```yaml
Type: SwitchParameter
Parameter Sets: SCXMaintenanceUserPassPriv, SCXMaintenanceSSHKeyPriv
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RunAsCredential
Specifies the credential for the Run As account.

```yaml
Type: PSCredential
Parameter Sets: Windows, Basic, Digest, Simple, ActionAccount, SCXMonitoring, SCXMaintenanceUserPassNoPrivSu, SCXMaintenanceUserPassNoPrivSudo, SCXMaintenanceUserPassPriv
Aliases: User

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter is not specified, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

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

### -SCXMaintenance
Indicates that the account is a cross-platform maintenance Run As account.

```yaml
Type: SwitchParameter
Parameter Sets: SCXMaintenanceUserPassNoPrivSu, SCXMaintenanceUserPassNoPrivSudo, SCXMaintenanceUserPassPriv, SCXMaintenanceSSHKeyNoPrivSu, SCXMaintenanceSSHKeyNoPrivSudo, SCXMaintenanceSSHKeyPriv
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCXMonitoring
Indicates that the Run As account is a Basic Authentication account, which uses basic web authentication.

```yaml
Type: SwitchParameter
Parameter Sets: SCXMonitoring
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Simple
Indicates that the account is a Simple Authentication Run As account.

```yaml
Type: SwitchParameter
Parameter Sets: Simple
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SnmpV3
Indicates that the account is an SNMP version 3 Run As account.

```yaml
Type: SwitchParameter
Parameter Sets: SnmpV3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -String
Specifies the account community string.

```yaml
Type: SecureString
Parameter Sets: CommunityString
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Su
Indicates that the cross-platform maintenance account uses superuser elevation to perform privileged actions.

```yaml
Type: SwitchParameter
Parameter Sets: SCXMaintenanceUserPassNoPrivSu, SCXMaintenanceSSHKeyNoPrivSu
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SuPassword
Specifies the superuser password for a cross-platform maintenance account.

```yaml
Type: SecureString
Parameter Sets: SCXMaintenanceUserPassNoPrivSu, SCXMaintenanceSSHKeyNoPrivSu
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sudo
Indicates that the cross-platform account uses sudo elevation to perform privileged actions.
The sudo program enables users to run programs that have the security permissions of another user account.

```yaml
Type: SwitchParameter
Parameter Sets: SCXMonitoring
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: SCXMaintenanceUserPassNoPrivSudo, SCXMaintenanceSSHKeyNoPrivSudo
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserName
Specifies the user name for the account.
This parameter is valid only for SNMP version 3 and cross-platform maintenance accounts.
Otherwise, use the *RunAsCredential* parameter.

```yaml
Type: String
Parameter Sets: SnmpV3, SCXMaintenanceSSHKeyNoPrivSu, SCXMaintenanceSSHKeyNoPrivSudo, SCXMaintenanceSSHKeyPriv
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Windows
Indicates that the account is a Run As account for Windows, which uses Windows credentials for authentication.
This is the default account type if the cmdlet does not specify a different type.

```yaml
Type: SwitchParameter
Parameter Sets: Windows
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Remove-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsAccount.md)

[Update-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMRunAsAccount.md)

