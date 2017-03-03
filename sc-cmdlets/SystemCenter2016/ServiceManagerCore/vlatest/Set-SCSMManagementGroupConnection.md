---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5691E524-10EF-42C2-9038-2D9260D3C917
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Set-SCSMManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Set-SCSMManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Set-SCSMManagementGroupConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSMManagementGroupConnection

## SYNOPSIS
Sets the active management group connection.

## SYNTAX

```
Set-SCSMManagementGroupConnection [-Connection] <Connection> [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSMManagementGroupConnection** cmdlet sets the specified connection as the active connection.
The active connection is the connection that is implicitly used when you run a **Get** cmdlet without specifying both a *ComputerName* parameter and a *Credential* parameter, or a SCSession parameter.
Only one connection can be active at any time.
By default, the active connection is the last connection that was created by using the **New-SCSMManagementGroupConnection** cmdlet.

## EXAMPLES

### Example 1: Activate a management group connection
```
PS C:\>Get-SCManagementGroupConnection
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                                                        False


PS C:\>Get-SCSMManagementGroupConnection | Set-SCSMManagementGroupConnection
PS C:\>Get-SCSMManagementGroupConnection
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                                                        True
```

These commands activate a management group connection.
The first command displays the **IsActive** state of the connection (**False**), and then the second command activates the connection.
The final command verifies the activation by displaying the **IsActive** state of the connection, which has now changed to **True**.

## PARAMETERS

### -Connection
Specifies the connection to activate.
You can specify only one connection.

```yaml
Type: Connection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.SystemCenter.Core.Connection.Connection
You can send a management group connection to the *Connection* parameter of the **Set-SCSMManagementGroupConnection** cmdlet by using the pipeline operator.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementGroupConnection.md)

[New-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementGroupConnection.md)

[Remove-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementGroupConnection.md)

