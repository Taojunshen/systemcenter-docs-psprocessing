---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239470
schema: 2.0.0
ms.assetid: 9BE130CF-43D2-4AAD-BED7-145C48D94C0C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMADAgentAssignment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMADAgentAssignment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMADAgentAssignment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMADAgentAssignment

## SYNOPSIS
Gets AD DS agent assignments for the management group.

## SYNTAX

### FromDomain (Default)
```
Get-SCOMADAgentAssignment [[-Domain] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementServer
```
Get-SCOMADAgentAssignment -PrimaryServer <ManagementServer[]> [[-Domain] <String[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMADAgentAssignment** cmdlet gets Active Directory Domain Services (AD DS) agent assignments for the management group.

## EXAMPLES

### Example 1: Get AD DS agent assignments by using a domain name
```
PS C:\>Get-SCOMADAgentAssignment -Domain "cdomain01.contoso.com"
```

This command gets all AD DS agent assignments for the domain named cdomain01.contoso.com.

### Example 2: Get AD DS agent assignments by using a primary server
```
PS C:\>Get-SCOMManagementServer "OMServer01*" | Get-SCOMADAgentAssignment -Domain "contoso.com"
```

This command gets AD DS agent assignments for a domain that have the same primary management server.
The command uses the **Get-SCOMManagementServer** cmdlet to get the management server named OMServer01, and passes the result to the **Get-SCOMADAgentAssignment** cmdlet by using the pipeline operator.
The command cmdlet gets all AD DS agent assignments for the domain named contoso.com that have the primary server named OMServer01.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be running on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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
For more information, type `Get-Help Get-Credential`.

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

### -Domain
Specifies the name of the domain or domain controller in which the target agents reside.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrimaryServer
Specifies an array of **ManagementServer** objects.
This parameter specifies the primary management servers for the target agent-managed computer.
To obtain a **ManagementServer** object, use the **Get-SCOMManagementServer** cmdlet.

```yaml
Type: ManagementServer[]
Parameter Sets: FromManagementServer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

A connection object represents a connection to a management server.
The default is the current management group connection.

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

[Add-SCOMADAgentAssignment](xref:OperationsManager/v1/Add-SCOMADAgentAssignment.md)

[Update-SCOMADAgentAssignment](xref:OperationsManager/v1/Update-SCOMADAgentAssignment.md)

[Remove-SCOMADAgentAssignment](xref:OperationsManager/v1/Remove-SCOMADAgentAssignment.md)
