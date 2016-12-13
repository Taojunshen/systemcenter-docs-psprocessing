---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187725
schema: 2.0.0
ms.assetid: 147C6753-2739-4337-9C3F-1F68ECAC91B3
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMUserRole

## SYNOPSIS
Gets user roles.

## SYNTAX

### Empty (Default)
```
Get-SCOMUserRole [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromUserRoleDisplayName
```
Get-SCOMUserRole [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromUserRoleId
```
Get-SCOMUserRole -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromUserRoleName
```
Get-SCOMUserRole -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMUserRole** cmdlet gets user roles.
A user role combines two elements: 

- Profile.
Defines the collection of operations to which the user role has access. 
- Scope.
Defines the boundaries for profile operations; for example, tasks and groups.

## EXAMPLES

### Example 1: Get user role information for a role
```
PS C:\>Get-SCOMUserRole -Name "OperationsManagerReadOnlyOperators"
```

This command gets the information for the user role named OperationsManagerReadOnlyOperators.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -DisplayName
Specifies an array that contains the display names of user role objects.
The cmdlet takes each string in the array and looks for matches among the display names of the user role objects that this cmdlet works with.
Values for this parameter vary depending on which localized management packs are imported into the management group and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromUserRoleDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an array of IDs for user role objects.
The cmdlet takes each globally unique identifier (GUID) in the array and looks for matches with the **ID** properties of the user role objects that the cmdlet gets.

```yaml
Type: Guid[]
Parameter Sets: FromUserRoleId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array that contains the names of user role objects.
The cmdlet takes each string in the array and looks for matches with the **Name** properties of the user role objects that the cmdlet gets.

```yaml
Type: String[]
Parameter Sets: FromUserRoleName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If you do not specify a value for this parameter, the cmdlet uses the active persistent connection to a management group.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCOMUserRole](xref:OperationsManager/v1/Add-SCOMUserRole.md)

[Set-SCOMUserRole](xref:OperationsManager/v1/Set-SCOMUserRole.md)

