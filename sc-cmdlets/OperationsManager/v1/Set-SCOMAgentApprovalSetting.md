---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239494
schema: 2.0.0
ms.assetid: 08FC816D-9051-4F00-A8B0-944C866585D0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentApprovalSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentApprovalSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMAgentApprovalSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMAgentApprovalSetting

## SYNOPSIS
Changes the manual agent approval setting for the management group.

## SYNTAX

### AutoReject (Default)
```
Set-SCOMAgentApprovalSetting [-AutoReject] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AutoApprove
```
Set-SCOMAgentApprovalSetting [-AutoApprove] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Pending
```
Set-SCOMAgentApprovalSetting [-Pending] [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMAgentApprovalSetting** cmdlet changes the manual agent approval setting for the management group.

Specify the *AutoApprove* parameter to automatically approve any new manually installed agents. 
Specify the *AutoReject* parameter to automatically reject any new manually installed agents. 
Specify the *Pending* parameter to review the request from any new manually installed agents.

## EXAMPLES

### Example 1: Change the agent approval setting to AutoApprove
```
PS C:\>Set-SCOMAgentApprovalSetting -AutoApprove
```

This command sets the manual agent approval setting for the management group to automatically approve any manually installed agent that contacts the management server and join the agent to the management group.

### Example 2: Change the agent approval setting to AutoReject
```
PS C:\>Set-SCOMAgentApprovalSetting -AutoReject
```

This command changes the manual agent approval setting for the management group to automatically reject any manually installed agent that contacts the management server.

### Example 3: Change the agent approval setting to Pending
```
PS C:\>Set-SCOMAgentApprovalSetting -Pending
```

This command changes the manual agent approval setting for the management group to pending.
An administrator must review the requests and manually approve the agent requests.

## PARAMETERS

### -AutoApprove
Indicates that Operations Manager automatically approves any manually installed agent that contacts the management server and joins the agent to the management group.

```yaml
Type: SwitchParameter
Parameter Sets: AutoApprove
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoReject
Indicates that Operations Manager automatically rejects any manually installed agent that contacts the management server and does not join the agent to the management group.

```yaml
Type: SwitchParameter
Parameter Sets: AutoReject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

### -Pending
Indicates that Operations Manager directs all requests from manually installed agents that contact the management server to the Pending Management list.
An administrator must review the request and manually approve the agent requests.

Use the **Get-SCOMPendingManagement**, **Approve-SCOMPendingManagement**, and **Deny-SCOMPendingManagement** cmdlets to manage agents in the pending management list.

```yaml
Type: SwitchParameter
Parameter Sets: Pending
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-SCOMAgentApprovalSetting](xref:OperationsManager/v1/Get-SCOMAgentApprovalSetting.md)

[Get-SCOMPendingManagement](xref:OperationsManager/v1/Get-SCOMPendingManagement.md)

[Approve-SCOMPendingManagement](xref:OperationsManager/v1/Approve-SCOMPendingManagement.md)

[Deny-SCOMPendingManagement](xref:OperationsManager/v1/Deny-SCOMPendingManagement.md)

