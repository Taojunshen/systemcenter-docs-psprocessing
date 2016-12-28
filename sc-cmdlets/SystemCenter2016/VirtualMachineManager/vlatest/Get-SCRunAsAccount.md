---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C0F6D0B8-75F5-4FA6-BF54-D3DDE2D98845
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCRunAsAccount

## SYNOPSIS
Gets VMM Run As accounts.

## SYNTAX

```
Get-SCRunAsAccount [-VMMServer <ServerConnection>] [-ID <Guid>] [[-Name] <String>] [-IsEnabled <Boolean>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCRunAsAccount** cmdlet gets Virtual Machine Manager (VMM) Run As accounts.

## EXAMPLES

### Example 1: Get a Run As account by its name
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $RunAsAccount variable.

The second command displays information about the Run As account stored in $RunAsAccount to the user.

### Example 2: Get an enabled Run As account by its name
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount01" -IsEnabled $True
PS C:\> $RunAsAccount
```

The first command gets the enabled Run As account object named RunAsAccount01 and stores the object in the $RunAsAccount variable.

The second command displays information about the Run As account stored in $RunAsAccount to the user.

### Example 3: Get enabled Run As accounts that contain a specified string in their name
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name *Account* -IsEnabled $True
PS C:\> $RunAsAccount[0]
PS C:\> $RunAsAccount[1]
```

The first command gets all enabled Run As account objects that contain Account in their names and stores the objects in the $RunAsAccount array.

The second command displays information about the first Run As account in the $RunAsAccount array to the user.

The third command displays information about the second Run As account in the $RunAsAccount array to the user.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

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

### -IsEnabled
Indicates whether this cmdlet retrieves Run As accounts that are enabled.
If you specify $False, the cmdlet returns Run Accounts that are disabled.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
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

### RunAsAccount
This cmdlet returns a **RunAsAccount** object.

## NOTES

## RELATED LINKS

[Disable-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Disable-SCRunAsAccount.md)

[Enable-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Enable-SCRunAsAccount.md)

[New-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCRunAsAccount.md)

[Remove-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCRunAsAccount.md)

[Set-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCRunAsAccount.md)

