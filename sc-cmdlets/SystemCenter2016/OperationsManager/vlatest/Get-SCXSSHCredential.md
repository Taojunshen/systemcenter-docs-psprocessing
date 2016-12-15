---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 3ffd34f8-0d88-4740-b321-323be5fb894c
schema: 2.0.0
ms.assetid: 74CC79EC-B0B6-48DB-B51A-2D068F34B089
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXSSHCredential.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXSSHCredential.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCXSSHCredential.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCXSSHCredential

## SYNOPSIS
Creates a privileged credential, by using the Secure Shell (SSH) protocol, for management operations on UNIX and Linux computers.

## SYNTAX

```
Get-SCXSSHCredential [-UserName] <String> [-SSHKey <String>] [-ElevationType <String>] [-SuppressWarning]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCXSSHCredential** cmdlet creates a credential for use in privileged UNIX or Linux SSH agent management operations.

## EXAMPLES

### Example 1: Create privileged credential
```
PS C:\>Get-SCXSSHCredential -UserName "root"
Password:  *************
```

This command creates a privileged SSH credential with a user name and prompts for a password.

### Example 2: Create privileged credential with su type
```
PS C:\>Get-SCXSSHCredential -UserName "DavidChew" -ElevationType su
Password:  *************
Su Password: *************
```

This command creates a low-privileged credential with a user name and su elevation type.
It then prompts for a password for the low-privileged account and the su password for the elevation.

### Example 3: Create privileged credential with sudo type
```
PS C:\>Get-SCXSSHCredential -UserName "DavidChew" -ElevationType sudo
Password: *************
```

This command creates a credential with a low-privileged account with a user name and a sudo elevation type.
It then prompts for a password for the low-privileged account.

### Example 4: Create privileged credential with passphrase
```
PS C:\>Get-SCXSSHCredential -UserName "root" -SSHKey "C:\keys\admin.ppk" 
Key Passphrase: *************
```

This command creates a privileged credential with a user name and an SSH key.
It then prompts for a passphrase.
If a passphrase was not configured with the SSH key, just press Enter.

### Example 5: Create privileged credential with su and passphrase
```
PS C:\>Get-SCXSSHCredential -UserName "DavidChew" -SSHKey "C:\keys\DavidChew.ppk" -ElevationType su 
Su Password: *************
Key Passphrase:
```

This command creates a low-privileged credential with a user name, an SSH key, and a su elevation type.
It then prompts for the su password and a key passphrase.

### Example 6: Create privileged credential with sudo and passphrase
```
C:\PS>Get-SCXSSHCredential -UserName "DavidChew" -SSHKey "C:\keys\DavidChew.ppk" -ElevationType sudo
Key Passphrase:
```

This command creates a low-privileged credential with a user name, an SSH key, and a sudo elevation type.
It then prompts for a key passphrase.

## PARAMETERS

### -ElevationType
Specifies the elevation method, either `su` or `sudo`, that elevates the supplied credential to a privileged account on the UNIX or Linux computer.
If left unspecified, the cmdlet treats the credential that is used to create the SSH connection as privileged.
If *ElevationType* is su, a root password must be provided for the *SuPassword* parameter.

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

### -SSHKey
Specifies the file name, including its path, of an SSH key.
The SSH key file must be in PuTTY key format.
This parameter is required unless a password is specified.

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

### -SuppressWarning
Indicates that this cmdlet suppresses warnings.

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

### -UserName
Specifies the user name for an SSH connection.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Unix.SSHCredential
This cmdlet returns the **SSHCredential** object as output.

## NOTES

## RELATED LINKS

