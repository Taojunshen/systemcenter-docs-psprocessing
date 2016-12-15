---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239453
schema: 2.0.0
ms.assetid: A5CC6446-8905-4018-ABF5-65FE0EE575CF
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMRunAsAccount

## SYNOPSIS
Removes a Run As account from the management group.

## SYNTAX

```
Remove-SCOMRunAsAccount [-RunAsAccount] <SecureData[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMRunAsAccount** cmdlet removes a Run As account from the management group.
A Run As account gives users the ability to specify permissions for rules, tasks, monitors, and discoveries that target specific computers on an as-needed basis.

The account cannot be part of any existing Run As profiles, or the command fails.

## EXAMPLES

### Example 1: Remove a Run As account
```
PS C:\>Get-SCOMRunAsAccount -Name "Contoso\Administrator" | Remove-SCOMRunAsAccount
```

This command removes the Contoso\Administrator Run As account.
The command uses the **Get-SCOMRunAsAccount** cmdlet to get the Run As account and passes it to the **Remove-SCOMRunAsAccount** cmdlet by using the pipeline operator.

## PARAMETERS

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

### -RunAsAccount
Specifies an array of **SecureData** objects that represent Run As accounts.
To obtain a **SecureData** object, use the **Get-SCOMRunAsAccount** cmdlet.
This account cannot be part of a Run As profile.

```yaml
Type: SecureData[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

[Add-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsAccount.md)

[Add-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsAccount.md)

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Update-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCOMRunAsAccount.md)

