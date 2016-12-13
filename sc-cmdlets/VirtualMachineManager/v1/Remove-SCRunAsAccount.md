---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Disable-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: 4EB59BAE-7B7F-4ABA-A282-D4192728985A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCRunAsAccount.md
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
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Remove-SCRunAsAccount -RunAsAccount $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $RunAsAccount variable.

The second command removes the Run As account stored in $RunAsAccount.

### Example 2: Remove a Run As account using the pipeline operator
```
PS C:\>Get-SCRunAsAccount -Name "RunAsAccount02" | Remove-SCRunAsAccount
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
To obtain a user role, use the Get-SCUserRole cmdlet.
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

[Disable-SCRunAsAccount](xref:VirtualMachineManager/v1/Disable-SCRunAsAccount.md)

[Enable-SCRunAsAccount](xref:VirtualMachineManager/v1/Enable-SCRunAsAccount.md)

[Get-SCRunAsAccount](xref:VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[New-SCRunAsAccount](xref:VirtualMachineManager/v1/New-SCRunAsAccount.md)

[Set-SCRunAsAccount](xref:VirtualMachineManager/v1/Set-SCRunAsAccount.md)

