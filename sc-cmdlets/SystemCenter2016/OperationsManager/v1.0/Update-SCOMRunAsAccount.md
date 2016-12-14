---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/?LinkId=245176
schema: 2.0.0
ms.assetid: 4C9FEF94-5762-4E91-894A-3AC6E4DF307C
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Update-SCOMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Update-SCOMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Update-SCOMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCOMRunAsAccount

## SYNOPSIS
Updates the credentials of an Operations Manager Run As account.

## SYNTAX

### WindowsAccount
```
Update-SCOMRunAsAccount [-WindowsAccount] <WindowsCredentialSecureData> [-RunAsCredential] <PSCredential>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BasicAccount
```
Update-SCOMRunAsAccount [-BasicAccount] <BasicCredentialSecureData> [-RunAsCredential] <PSCredential>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SimpleAccount
```
Update-SCOMRunAsAccount [-SimpleAccount] <SimpleCredentialSecureData> [-RunAsCredential] <PSCredential>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DigestAccount
```
Update-SCOMRunAsAccount [-DigestAccount] <DigestCredentialSecureData> [-RunAsCredential] <PSCredential>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ActionAccount
```
Update-SCOMRunAsAccount [-ActionAccount] <ActionAccountSecureData> [-RunAsCredential] <PSCredential>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CommunityStringAccount
```
Update-SCOMRunAsAccount [-CommunityStringAccount] <CommunityStringSecureData> [-CommunityString] <SecureString>
 [-AccountType <String>] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BinaryAccount
```
Update-SCOMRunAsAccount [-BinaryAccount] <GenericSecureData> [-Path] <String> [-AccountType <String>]
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCOMRunAsAccount** cmdlet updates the credentials of an System Center 2016 - Operations Manager Run As account.
A Run As account gives users the ability to specify the necessary permissions for use with rules, tasks, monitors, and discoveries targeted to specific computers on an as-needed basis.

This cmdlet does not support SCX (cross-platform) accounts or Simple Network Management Protocol version 3 (SNMPv3) accounts.

## EXAMPLES

### Example 1: Update a Windows Run As account
```
PS C:\>$WindowsAccount = Get-SCOMRunAsAccount -Name "Domain Admin"
PS C:\> $WindowsAccount | Update-SCOMRunAsAccount -RunAsCredential (Get-Credential)
```

This example updates a Windows Run As account.

The first command gets the Run As account object named Domain Admin and stores the object in the $WindowsAccount variable.

The second command passes the Run As account stored in the $WindowsAccount variable to the **Update-SCOMRunAsAccount** cmdlet by using the pipeline operator.
That cmdlet updates the credentials for the account to the user name and password that the user provides by responding to the prompt from the **Get-Credential** cmdlet.

### Example 2: Update an action Run As account
```
PS C:\>$UserName = "Contoso\SCOMActionAccount"
PS C:\> $Password = Read-Host -AsSecureString
PS C:\> $NewCred = new-object System.Management.Automation.PsCredential $UserName,$Password
PS C:\> Get-SCOMRunAsAccount -Name "SCOM Action Account" | Update-SCOMRunAsAccount -RunAsCredential $newCred
```

This example updates credentials for an action Run As account.

The first command creates a string that contains an action account name and stores the string in the $UserName variable.

The second command prompts the user to enter a string that represents the password.
It then stores the user input as a secure string in the $Password variable.

The third command creates a **PSCredential** object by using the name stored in the $UserName variable and the password stored in $Password.
It then stores the **PSCredential** object in the $NewCred variable.

The last command gets the action account named SCOM Action Account.
It then uses the pipeline operator to pass the account to the **Update-SCOMRunAsAccount** cmdlet, which updates the account with the credentials stored in the $NewCred variable.

### Example 3: Update a Community String account
```
PS C:\>Get-SCOMRunAsAccount -Name "MyCommunityStringAccount" | Update-SCOMRunAsAccount -CommunityString (Read-Host -AsSecureString)
```

This command updates credentials for a Run As account that uses community string authentication for SNMP version 2.
It gets the community string account named MyCommunityStringAccount and uses the pipeline operator to pass the account to the **Update-SCOMRunAsAccount** cmdlet.
This cmdlet updates the community string with the value that the user enters in response to prompts from the **Read-Host** cmdlet.
For more information, type `Get-Help Read-Host`.

### Example 4: Update a Binary Authentication account
```
PS C:\>Get-SCOMRunAsAccount -Name "MyBinaryAccount" | Update-SCOMRunAsAccount -Path ".\data.txt"
```

This example gets the binary account object named MyBinaryAccount and uses the pipeline operator to pass the object to the **Update-SCOMRunAsAccount** cmdlet.
This cmdlet uses the *Path* parameter to indicate that it gets the new account data from the file named data.txt.

## PARAMETERS

### -AccountType
Specifies the type of the Run As account.
The pipeline typically populates this value automatically.

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

### -ActionAccount
Specifies an action account as a Run As account.

```yaml
Type: ActionAccountSecureData
Parameter Sets: ActionAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BasicAccount
Specifies a Run As account that uses Basic Authentication.

```yaml
Type: BasicCredentialSecureData
Parameter Sets: BasicAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -BinaryAccount
Specifies a Run As account that uses Binary Authentication.

```yaml
Type: GenericSecureData
Parameter Sets: BinaryAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CommunityString
Specifies the new community string for an SNMP version 2 Run As account that uses community string authentication.

```yaml
Type: SecureString
Parameter Sets: CommunityStringAccount
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommunityStringAccount
Specifies an SNMP version 2 Run As account that uses community string authentication.

```yaml
Type: CommunityStringSecureData
Parameter Sets: CommunityStringAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -DigestAccount
Specifies a Run As account that uses standard digest web authentication.

```yaml
Type: DigestCredentialSecureData
Parameter Sets: DigestAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

### -Path
Specifies the path to a file that contains new credential data for Run As accounts that use Binary Authentication.

```yaml
Type: String
Parameter Sets: BinaryAccount
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsCredential
Specifies new credentials for account types that use a username and password.

```yaml
Type: PSCredential
Parameter Sets: WindowsAccount, BasicAccount, SimpleAccount, DigestAccount, ActionAccount
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
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

### -SimpleAccount
Specifies a Run As account that uses simple web authentication.

```yaml
Type: SimpleCredentialSecureData
Parameter Sets: SimpleAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WindowsAccount
Specifies a Run As account that uses Windows authentication.

```yaml
Type: WindowsCredentialSecureData
Parameter Sets: WindowsAccount
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Add-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/v1.0/Add-SCOMRunAsAccount.md)

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMRunAsAccount.md)

