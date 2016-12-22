---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8E6BF2A2-71F0-4467-A388-357668A568DF
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCOMResourcePool

## SYNOPSIS
Creates a resource pool in Operations Manager.

## SYNTAX

```
New-SCOMResourcePool [-DisplayName] <String> [-Member] <ComputerHealthService[]>
 [-Observer <ComputerHealthService[]>] [-Description <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCOMResourcePool** cmdlet creates a resource pool in System Center 2016 - Operations Manager.
A resource pool enables a collection of management servers to distribute the workload.

## EXAMPLES

### Example 1: Create a resource pool
```
PS C:\>New-SCOMResourcePool -DisplayName "Pool01" -Member (Get-SCOMManagementServer) -PassThru
```

This example creates a resource pool named Pool01 that contains all management servers.

The command in parentheses, which is executed first, uses the **Get-SCOMmanagementServer** cmdlet to get all management servers.
The cmdlet then passes the results of the command in parentheses to the **New-SCOMResourcePool** cmdlet, which creates the resource pool and adds the management servers.

Note: Because the management servers are added to this resource pool manually, this resource pool will not have automatic membership enabled, and you must add all future members manually.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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
For more information, type "`Get-Help Get-Credential`".If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
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

### -Description
Specifies a description for the resource pool.
The parameter accepts a maximum character length of 4,000 characters.

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

### -DisplayName
Specifies a display name of an object.
Values of the *DisplayName* parameter may vary depending on which localized management packs a user imports into the management group and the locale of the user who is running Windows PowerShell

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Member
Specifies an array of objects to include in the resource pool.

Valid objects that can be members of a resource pool include management servers or gateway servers.
For information about how to get a gateway server object, type "`Get-Help Get-SCOMGatewayManagementServer`".

```yaml
Type: ComputerHealthService[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Observer
Specifies an array of management servers or gateway management servers not currently in a resource pool.

To make a resource pool highly available, you must add a minimum of three members to the pool, or two members and one observer.

```yaml
Type: ComputerHealthService[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[New-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md)

[Remove-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMResourcePool.md)

[Set-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMResourcePool.md)

