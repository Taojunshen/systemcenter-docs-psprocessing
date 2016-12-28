---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5E2FDA00-D52C-4031-8818-D95BFEE4BD90
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMEvent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMEvent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMEvent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMEvent

## SYNOPSIS
Gets Operations Manager events.

## SYNTAX

### Empty (Default)
```
Get-SCOMEvent [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromEventId
```
Get-SCOMEvent [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromInstance
```
Get-SCOMEvent [-Instance] <EnterpriseManagementObject[]> [[-EventId] <Int32[]>] [[-EventLogName] <String[]>]
 [[-EventSource] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackRule
```
Get-SCOMEvent [-Rule] <ManagementPackRule[]> [[-EventId] <Int32[]>] [[-EventLogName] <String[]>]
 [[-EventSource] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMEvent** cmdlet gets System Center 2016 - Operations Manager events.
Rules collect events.

You can specify events by ID or by the managed object.
You can also specify the rule that the event triggers.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Get events for WMI rules
```
PS C:\>$Rules = Get-SCOMRule -Name *WMI*
PS C:\> Get-SCOMClass -DisplayName *health* | Get-SCOMClassInstance | Get-SCOMEvent -Rule $Rules -ErrorAction SilentlyContinue
```

This example gets all the health events matching rules that contain WMI in their display names.
The first command gets all monitoring rules that have WMI in their display names and stores them in the $Rules variable.

The second command gets all classes with health in the display name and uses the pipeline operator (|) to pass the class objects to the **Get-SCOMClassInstance** cmdlet.
That cmdlet gets the class instances for each of the class objects.
Then, the command gets the events for each class instance matching the rules stored in the $Rules variable.
Using the *ErrorAction* parameter with a value of SilentlyContinue allows the command to continue if it does not find an event that matches the specified rule.

### Example 2: Get an event by using its ID
```
PS C:\>Get-SCOMEvent -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the event that has an ID of 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

### Example 3: View events grouped by event IDs
```
PS C:\>Get-SCOMEvent | Group-Object -Property Number
```

This command gets all events and then passes them to the **Group-Object** cmdlet by using the pipeline operator.
That cmdlet displays the events grouped by the **Number** property of the **SCOMEvent** object, which corresponds to an integer event ID.
For more information, type `Get-Help Group-Object`.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
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

### -EventId
Specifies an array of event IDs.
An **SCOMEvent** object contains an event ID as its **Number** property.

```yaml
Type: Int32[]
Parameter Sets: FromInstance, FromManagementPackRule
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -EventLogName
Specifies an array of names of event logs.
An **SCOMEvent** object contains an event log name as its **Channel** property.

```yaml
Type: String[]
Parameter Sets: FromInstance, FromManagementPackRule
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -EventSource
Specifies an array of event sources.
An **SCOMEvent** object contains an event source as its **PublisherName** property.

```yaml
Type: String[]
Parameter Sets: FromInstance, FromManagementPackRule
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies an array of GUIDs of events.
An **SCOMEvent** object contains GUID as its **Id** property.

```yaml
Type: Guid[]
Parameter Sets: FromEventId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent instances.
To obtain monitoring objects, use the **Get-SCOMClassInstance** cmdlet.

This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromInstance
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Rule
Specifies an array of rules as **ManagementPackRule** objects.
To obtain a **ManagementPackRule** object, use the **Get-SCOMRule** cmdlet.

```yaml
Type: ManagementPackRule[]
Parameter Sets: FromManagementPackRule
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMRule](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRule.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

