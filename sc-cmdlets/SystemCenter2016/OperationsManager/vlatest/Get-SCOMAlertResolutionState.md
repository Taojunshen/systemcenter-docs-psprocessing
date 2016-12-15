---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239473
schema: 2.0.0
ms.assetid: BEA81B65-62C8-4962-9D01-B14A29C2226C
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertResolutionState.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertResolutionState.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlertResolutionState.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMAlertResolutionState

## SYNOPSIS
Gets the alert resolution states in the management group.

## SYNTAX

### Empty (Default)
```
Get-SCOMAlertResolutionState [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementState
```
Get-SCOMAlertResolutionState -ResolutionStateCode <Byte[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromName
```
Get-SCOMAlertResolutionState -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAlertResolutionState** cmdlet gets the alert resolution states in the management group.
Each resolution state is assigned an ID, a code number which uniquely identifies that resolution state.
The ID for New is 0 and the ID for Closed is 255.
You can assign custom resolution states any value from 2 through 254.

## EXAMPLES

### Example 1: Get all resolution states
```
PS C:\>Get-SCOMAlertResolutionState
```

This command gets all resolution states in the management group.

### Example 2: Get resolution states by using a resolution state code
```
PS C:\>Get-SCOMAlertResolutionState -ResolutionStateCode 42
```

This command gets information about the resolution state that has the code 42.

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

### -Name
Specifies an array of names of alert resolution states.

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResolutionStateCode
Specifies a resolution state ID.

Operations Manager defines two resolution states: New (0) and Closed (255).
You can assign custom resolution states any value from 2 through 254.

```yaml
Type: Byte[]
Parameter Sets: FromManagementState
Aliases: ResolutionState

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Add-SCOMAlertResolutionState](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMAlertResolutionState.md)

[Remove-SCOMAlertResolutionState](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMAlertResolutionState.md)

