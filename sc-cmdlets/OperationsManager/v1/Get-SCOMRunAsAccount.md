---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=239449
schema: 2.0.0
ms.assetid: E6002A38-4A7E-4617-8A73-1A8FF363D645
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMRunAsAccount

## SYNOPSIS
Gets a Run As account for a management group.

## SYNTAX

### EmptyParameterSet (Default)
```
Get-SCOMRunAsAccount [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRunAsAccountName
```
Get-SCOMRunAsAccount [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCOMRunAsAccount -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMRunAsAccount** cmdlet gets Run As accounts for a System Center 2016 - Operations Manager management group.
A Run As account gives users the ability to specify the necessary permissions for use with rules, tasks, monitors, and discoveries targeted to specific computers on an as-needed basis.

## EXAMPLES

### Example 1: Get all action accounts
```
PS C:\>Get-SCOMRunAsAccount
```

This command gets all action accounts.

### Example 2: Get all data warehouse accounts
```
PS C:\>Get-SCOMRunAsAccount -Name "Data Warehouse*"
```

This command gets all accounts whose names begin with Data Warehouse.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, specify the computer name, localhost, or a dot (.).

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
For more information about credential objects, type Get-Help Get-Credential.

This account must have access to the server that is specified in the *ComputerName* parameter if that parameter appears.

If you do not specify this parameter, the default is the account for the current user.

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

### -Id
Specifies an array of account IDs.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of account names.

```yaml
Type: String[]
Parameter Sets: FromRunAsAccountName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter does not appear, the cmdlet uses the active persistent connection to a management group.
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

[Add-SCOMRunAsAccount](xref:OperationsManager/v1/Add-SCOMRunAsAccount.md)

[Get-SCManagementGroupConnection](xref:OperationsManager/v1/Get-SCManagementGroupConnection.md)

[Remove-SCOMRunAsAccount](xref:OperationsManager/v1/Remove-SCOMRunAsAccount.md)

[Update-SCOMRunAsAccount](xref:OperationsManager/v1/Update-SCOMRunAsAccount.md)

