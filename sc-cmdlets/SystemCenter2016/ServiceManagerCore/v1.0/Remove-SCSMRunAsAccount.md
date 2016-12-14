---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225417
schema: 2.0.0
ms.assetid: C9B78666-1511-4A74-8493-AA8C12837FBE
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMRunAsAccount

## SYNOPSIS
Removes a RunAs account.

## SYNTAX

```
Remove-SCSMRunAsAccount [-RunAsAccount] <UserAccount[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMRunAsAccount** cmdlet removes a RunAs account.

## EXAMPLES

### Example 1: Remove RunAs accounts by name
```
PS C:\>Get-SCSMRunAsAccount | Where-Object {$_.UserName -eq "Administrator"}|Remove-SCSMRunAsAccount
```

This command removes all RunAs accounts in which the user name is "Administrator".
Note that this may cause certain workflows and other operations to fail.

## PARAMETERS

### -RunAsAccount
Specifies the RunAs account to be removed.
Input to this parameter can be a **ManagementPackSecureReference** object or a **UserAccount** object that, for example, you can obtain from the **Get-SCSMRunAsAccount** cmdlet.

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
You can pipe a **RunAsAccount** object to the **RunAsAccount** parameter of the **Remove-SCSMRunAsAccount** cmdlet, for example, the object that is retrieved by the **Get-SCRunAsAccount** cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/v1.0/Get-SCSMRunAsAccount.md)

[New-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/v1.0/New-SCSMRunAsAccount.md)

[Update-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/v1.0/Update-SCSMRunAsAccount.md)

