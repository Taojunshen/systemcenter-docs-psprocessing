---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=199892
schema: 2.0.0
ms.assetid: 7A74BFB1-CA2B-4A90-990F-9CA0FF1A0BBE
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMResourcePool

## SYNOPSIS
Removes one or more resource pools in Operations Manager.

## SYNTAX

```
Remove-SCOMResourcePool [-ResourcePool] <ManagementServicePool[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMResourcePool** cmdlet removes one or more resource pools in System Center 2016 - Operations Manager.
A resource pool enables a collection of management servers to distribute the workload.

This cmdlet requires a **SCOMResourcePool** object.
For information about how to get a resource pool object, type "`Get-Help Get-SCOMResourcePool`".

## EXAMPLES

### Example 1: Remove a resource pool
```
PS C:\>Get-SCOMResourcePool -DisplayName "Pool01*" | Remove-SCOMResourcePool -Confirm
```

This command retrieves all resource pools that have a display name that begins with the string Pool01.
The command uses the pipeline operator to pass the resource pool objects to the **Remove-SCOMResourcePool** cmdlet and prompts the user for confirmation before removing the resource pool.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name,  localhost, or a dot (.).

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
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type "`Get-Help Get-Credential`".

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

### -ResourcePool
Specifies an array of resource pool objects.
For information about how to get a resource pool object, type "`Get-Help Get-SCOMResourcePool`".

```yaml
Type: ManagementServicePool[]
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
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

[Get-SCOMResourcePool](xref:OperationsManager/v1/Get-SCOMResourcePool.md)

[New-SCOMResourcePool](xref:OperationsManager/v1/New-SCOMResourcePool.md)

[Set-SCOMResourcePool](xref:OperationsManager/v1/Set-SCOMResourcePool.md)

