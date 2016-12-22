---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 878A3BAF-3EA9-4487-85C6-53D7A62CC59D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementGroupConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementGroupConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementGroupConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMManagementGroupConnection

## SYNOPSIS
Creates a connection for a management group.

## SYNTAX

```
New-SCSMManagementGroupConnection [[-ComputerName] <String[]>] [[-Credential] <PSCredential>] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMManagementGroupConnection** cmdlet creates a connection for a management group.
The last connection that is created with the **New-SCSMManagementGroupConnection** cmdlet becomes the active connection that is used by the **Get** cmdlets when no **ComputerName** or **SCSession** parameter is specified.
You can use the **Set-SCManagementGroupConnection** cmdlet to set a different active connection.
If a connection already exists, this cmdlet does not create a new connection.

## EXAMPLES

### Example 1: Create a management group connection
```
PS C:\>New-SCSMManagementGroupConnection -ComputerName "localhost" -Credential (Get-Credential CONTOSO\Administrator)
PS C:\>Get-SCManagementGroupConnection
ManagementServerName    ManagementGroupName                 Domain          UserName             IsActive
--------------------    -------------------                 ------          --------             --------
localhost               MyMangementGroup                                                         False
localhost               MyMangementGroup                    CONTOSO         Administrator        True
```

These commands create a management group connection.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: Localhost
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.
The default value is the current user.

You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies the output object that represents the new session.
This output object can be passed to other cmdlets.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a computer name to the *ComputerName* parameter of the **New-SCSMManagementGroupConnection** cmdlet.

## OUTPUTS

### Connection object.
This cmdlet can generate a connection object when it is used with the *PassThru* parameter.

## NOTES

## RELATED LINKS

[Get-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementGroupConnection.md)

[Remove-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementGroupConnection.md)

[Set-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/vlatest/Set-SCSMManagementGroupConnection.md)

