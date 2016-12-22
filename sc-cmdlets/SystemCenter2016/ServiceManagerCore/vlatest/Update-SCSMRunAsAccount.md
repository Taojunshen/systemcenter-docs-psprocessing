---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CF0558DF-2A62-43D5-A80A-064104CA8345
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCSMRunAsAccount

## SYNOPSIS
Updates RunAs account credentials.

## SYNTAX

```
Update-SCSMRunAsAccount [-PassThru] [-RunAsAccount] <UserAccount[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMRunAsAccount** cmdlet updates the credentials that are associated with a RunAs account.
Use this cmdlet to change the stored credentials for a RunAs account when that account's user name or password changes.
Passwords are securely stored so that impersonation can take place for workflows and other operations.

## EXAMPLES

### Example 1: Changes a RunAs account password
```
PS C:\>$Credential = Get-Credential
PS C:\>$Account = Get-SCSMRunAsAccount â€"UserName "Administrator"
PS C:\>$Account.Password = $Credential.Password
PS C:\>$Account | Update-SCSMRunAsAccount
```

These commands set the RunAs account password according to the supplied credential object.

## PARAMETERS

### -PassThru
Specifies the output object that represents the RunAs account to update.
This output object can be passed to other cmdlets.

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

### -RunAsAccount
Specifies the object that represents the RunAs account.
It contains the RunAs account name and the credentials that are associated with that account.

```yaml
Type: UserAccount[]
Parameter Sets: (All)
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

### Microsoft.EnterpriseManagement.Core.SdkUtilities.Security.UserAccount
You can pipe a RunAs account object to the *RunAsAccount* parameter of the **Update-SCSMRunAsAccount** cmdlet, for example, the object that is returned by the **Get-SCRunAsAccount** cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMRunAsAccount.md)

[New-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMRunAsAccount.md)

[Remove-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMRunAsAccount.md)

