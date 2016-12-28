---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 01EDFF01-AD02-4AAD-9C90-E4D0BC02F784
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMUserRole

## SYNOPSIS
Removes a user role from Service Manager.

## SYNTAX

```
Remove-SCSMUserRole [-UserRole] <Role[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMUserRole** cmdlet removes a user role from Service Manager.
Some user roles are designated as system user roles, and cannot be removed.
You can run the following command to display the **issystem** attribute of all user role objects.

`Get-SCSMUserRole | Format-Table -Property DisplayName,{$_.userrole.issystem} -AutoSize`

If the user role cannot be removed, this cmdlet returns a non-terminating error.

## EXAMPLES

### Example 1: Remove a user role
```
PS C:\>Get-SCSMUserRole -Name "CustomUser" | Remove-SCSMUserRole
```

This command gets the user role named CustomUser by using the Get-SCSMUserRole cmdlet.
The command passes that object to the current cmdlet by using the pipeline operator.
That cmdlet deletes that user role.

## PARAMETERS

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

### -UserRole
Specifies the **UserRole** object from which to remove the user.

```yaml
Type: Role[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.UserRoles.Role
You can pipe a user role to the *UserRole* parameter.
For example, an object such as that returned by the Get-SCSMUserRole cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMUserRole.md)

[New-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMUserRole.md)

[Update-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMUserRole.md)

