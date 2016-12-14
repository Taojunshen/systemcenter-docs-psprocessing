---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225403
schema: 2.0.0
ms.assetid: BDC27D40-F5BF-403C-B6AA-15525A0B70A6
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Get-SCSMManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Get-SCSMManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Get-SCSMManagementGroupConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMManagementGroupConnection

## SYNOPSIS
Gets all management group connections.

## SYNTAX

### Empty (Default)
```
Get-SCSMManagementGroupConnection [<CommonParameters>]
```

### FromComputerNames
```
Get-SCSMManagementGroupConnection [-ComputerName] <String[]> [<CommonParameters>]
```

### FromInstanceId
```
Get-SCSMManagementGroupConnection [-Id] <Guid[]> [<CommonParameters>]
```

### FromManagementGroupName
```
Get-SCSMManagementGroupConnection [-ManagementGroupName] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMManagementGroupConnection** cmdlet retrieves all management group connections, including the **IsActive** state of these connections.
Only one connection will have its **IsActive** state set to **True**, because only one connection can be active at any time.

## EXAMPLES

### Example 1: Get all available management group connections
```
PS C:\>Get-SCSMManagementGroupConnection


ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyManagementGroup                                                        True
```

This command retrieves all the available management group connections.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

```yaml
Type: String[]
Parameter Sets: FromComputerNames
Aliases: 

Required: True
Position: 1
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of a management group for which to retrieve connections.

```yaml
Type: Guid[]
Parameter Sets: FromInstanceId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementGroupName
Specifies the names of the management groups for which to retrieve connections.

```yaml
Type: String[]
Parameter Sets: FromManagementGroupName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a computer name to the *ComputerName* parameter of the **Get-SCSMManagementGroupConnection** cmdlet.

## OUTPUTS

### SessionObject
This cmdlet generates a **SessionObject** object.

## NOTES

## RELATED LINKS

[New-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/v1.0/New-SCSMManagementGroupConnection.md)

[Remove-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMManagementGroupConnection.md)

[Set-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/v1.0/Set-SCSMManagementGroupConnection.md)

