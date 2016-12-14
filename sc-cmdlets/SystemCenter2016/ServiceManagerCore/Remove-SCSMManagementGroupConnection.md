---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225415
schema: 2.0.0
ms.assetid: F116FA36-520D-45AF-AF5D-65791ED3A0A8
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMManagementGroupConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMManagementGroupConnection

## SYNOPSIS
Removes a management group connection.

## SYNTAX

```
Remove-SCSMManagementGroupConnection [-Connection] <Connection[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMManagementGroupConnection** cmdlet removes a management group connection.

## EXAMPLES

### Example 1: Display and remove management server sessions
```
PS C:\>Get-SCSMManagementGroupConnection
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                                                        False
localhost               MyManagementGroup                   CONTOSO         Administrator        True


PS C:\>Get-SCSMManagementGroupConnection |?{$_.IsActive }
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                   CONTOSO         Administrator        True


PS C:\>Get-SCSMManagementGroupConnection |?{$_.IsActive } | Remove-SCSMManagementGroupConnection
PS C:\>Get-SCSMManagementGroupConnection
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                                                        False
```

These commands display management server sessions, remove the active management server session, and then display the available sessions to verify the removal.

## PARAMETERS

### -Connection
Specifies the connection, originating from the **Get-SCSMManagementGroupConnection** cmdlet, to be removed.

```yaml
Type: Connection[]
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

### Microsoft.SystemCenter.Core.Connection.Connection
You can pipe a management group connection to the *Connection* parameter of the cmdlet.

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMManagementGroupConnection.md)

[New-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/New-SCSMManagementGroupConnection.md)

[Set-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/Set-SCSMManagementGroupConnection.md)

