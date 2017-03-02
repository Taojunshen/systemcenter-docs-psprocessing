---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 584D533D-9B5E-4D90-8232-B84C10D7D035
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMPendingManagement.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMPendingManagement.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMPendingManagement.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMPendingManagement

## SYNOPSIS
Retrieves pending agent management actions.

## SYNTAX

```
Get-SCOMPendingManagement [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMPendingManagement** cmdlet retrieves pending agent management actions in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Retrieve all pending management entries
```
PS C:\>Get-SCOMPendingManagement | Sort AgentName
```

This command uses the **Get-SCOMPendingManagement** cmdlet to retrieve all pending management entries and sort them by the AgentName property.

### Example 2: Retrieve pending management entries for a specific action
```
PS C:\>Get-SCOMPendingManagement | where {$_.AgentPendingActionType -eq "ManualApproval"} | Sort AgentName
```

This command uses the **Get-SCOMPendingManagement** cmdlet to get the agent management entries that are pending with an action of ManualApproval, and sort the returned entries by the AgentName property.

### Example 3: Retrieve pending management entries and group by name
```
PS C:\>Get-SCOMPendingManagement | Group AgentPendingActionType | Sort -Descending Count | Select-object Name, Count
```

This command uses the **Get-SCOMPendingManagement** cmdlet to get all pending management entries, group them by their pending action type, and then sort them in descending order by the number of entries there are per action type group.
The command then returns the action type group name and number of entries in each group.

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
For more information, type "`Get-Help Get-Credential`".

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Approve-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/vlatest/Approve-SCOMPendingManagement.md)

[Deny-SCOMPendingManagement](xref:SystemCenter2016/OperationsManager/vlatest/Deny-SCOMPendingManagement.md)

