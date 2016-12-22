---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4EB59BAE-7B7F-4ABA-A282-D4192728985A
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCRunAsAccount

## SYNOPSIS
Removes a VMM Run As account.

## SYNTAX

```
Remove-SCRunAsAccount [-VMMServer <ServerConnection>] [-RunAsAccount] <RunAsAccount> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCRunAsAccount** cmdlet removes a Run As account from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove a Run As account
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Remove-SCRunAsAccount -RunAsAccount $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $RunAsAccount variable.

The second command removes the Run As account stored in $RunAsAccount.

### Example 2: Remove a Run As account using the pipeline operator
```
PS C:\> Get-SCRunAsAccount -Name "RunAsAccount02" | Remove-SCRunAsAccount
```

This command gets the Run As account object named RunAsAccount02 and uses the pipeline operator to pass the object to the **Remove-SCRunAsAccount** cmdlet, which removes the account.

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

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

[Disable-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCRunAsAccount.md)

[Enable-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCRunAsAccount.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[New-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCRunAsAccount.md)

[Set-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCRunAsAccount.md)

