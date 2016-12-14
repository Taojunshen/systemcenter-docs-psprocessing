---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: BCE90081-CD6B-44CA-B945-021ED8071157
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCRunAsAccountConsumer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCRunAsAccountConsumer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCRunAsAccountConsumer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCRunAsAccountConsumer

## SYNOPSIS
Gets the Run As account consumer objects for a specified Run As account.

## SYNTAX

```
Get-SCRunAsAccountConsumer [-VMMServer <ServerConnection>] [[-RunAsAccount] <RunAsAccount>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCRunAsAccountConsumer** cmdlet gets the Run As account consumer objects for a specified Run As account.
**Get-SCRunAsAccountConsumer** returns any Virtual Machine Manager (VMM) object that refers to the given Run As account.

## EXAMPLES

### Example 1: Get the load balancers that use a specified Run As account
```
PS C:\>$RunAsAcct = Get-SCRunAsAccount -Name "LBRunAsAcct01" 
PS C:\> $RAAConsumers = Get-SCRunAsAccountConsumer -RunAsAccount $RunAsAcct
PS C:\> $RAAConsumers
```

The first command gets the Run As account object named LBRunAsAcct01 and stores the object in the $RunAsAcct variable.

The second command gets the Run As account consumer objects for the load balancers that use the Run As account stored in $RunAsAcct and stores the consumer objects in the $RAAConsumers variable.

The last command displays the Run As account consumer objects stored in $RAAConsumers to the user.

## PARAMETERS

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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: False
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

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:VirtualMachineManager/v1/Get-SCRunAsAccount.md)
