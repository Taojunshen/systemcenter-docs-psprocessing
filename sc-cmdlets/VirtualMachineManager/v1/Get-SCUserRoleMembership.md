---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUserRole.md
schema: 2.0.0
ms.assetid: 7139D64C-8AC1-42EA-8CBC-852A16F4BF48
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUserRoleMembership.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUserRoleMembership.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCUserRoleMembership.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCUserRoleMembership

## SYNOPSIS
Gets information about user roles of which a user is a member.

## SYNTAX

```
Get-SCUserRoleMembership [-VMMServer <ServerConnection>] [[-UserName] <String>] [-Resource <ClientObject>]
 [-ForSharing] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUserRoleMembership** cmdlet gets information about the user roles of which the current user or a specified user is a member.

## EXAMPLES

### Example 1: Get information about user roles for current user
```
PS C:\>Get-SCUserRoleMembership
```

This command returns the name, description, and user role profile for each user role of which the current user is a member.

## PARAMETERS

### -ForSharing
Indicates that this cmdlet gets only self-service user roles to which the user belongs that can share resources.

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

### -Resource
Specifies a resource object.

```yaml
Type: ClientObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies the name of a user for which this cmdlet gets user roles.
Enter a user name in the format Domain\User.

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

### -VMMServer
Specifies a VMM server on which this cmdlet gets user roles.

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

### UserRoleMembership
This cmdlet returns a **UserRoleMembership** object.

## NOTES

## RELATED LINKS

[Get-SCUserRole](xref:VirtualMachineManager/v1/Get-SCUserRole.md)

[New-SCUserRole](xref:VirtualMachineManager/v1/New-SCUserRole.md)

[Remove-SCUserRole](xref:VirtualMachineManager/v1/Remove-SCUserRole.md)

[Set-SCUserRole](xref:VirtualMachineManager/v1/Set-SCUserRole.md)

