---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 8d9923c5-8694-42e7-9500-67c20cd28bc5
schema: 2.0.0
ms.assetid: 41EBD541-2A84-44B3-B0EB-E33623CBFB4E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCDomainCredential.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCDomainCredential.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCDomainCredential.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCDomainCredential

## SYNOPSIS
Tests a credential or user name to verify that it authenticates in the domain.

## SYNTAX

### Credential
```
Test-SCDomainCredential [-VMMServer <ServerConnection>] [-Credential] <VMMCredential> [<CommonParameters>]
```

### UserName
```
Test-SCDomainCredential [-VMMServer <ServerConnection>] [-UserName] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCDomainCredential** cmdlet tests a credential object or user name to verify that it authenticates in the domain.

## EXAMPLES

### Example 1: Test the validity of a credential object
```
PS C:\> $Creds = Get-Credential
PS C:\> Test-SCDomainCredential -Credential $Creds
```

The first command prompts you for a username and password, creates a **PSCredential** object, and stores the object in the $Creds variable.

The second command validates the credential object in $Creds and returns either True or False.

### Example 2: Test the validity of a user name
```
PS C:\> Test-SCDomainCredential -UserName "PattiFuller"
```

This command tests the validity of the user name PattiFuller and returns either True or False.

## PARAMETERS

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the PSCredential object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: Credential
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserName
Specifies a the name of a user.
Enter a user name with the format Domain\User.

```yaml
Type: String
Parameter Sets: UserName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Boolean
This cmdlet returns a Boolean result.

## NOTES

## RELATED LINKS

