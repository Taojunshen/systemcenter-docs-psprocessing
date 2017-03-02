---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F9324579-3123-489E-950A-4420A067DCF8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTask.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTask.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTask.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMTask

## SYNOPSIS
Gets a list of tasks.

## SYNTAX

### Empty (Default)
```
Get-SCOMTask [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromTaskDisplayName
```
Get-SCOMTask [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromTaskId
```
Get-SCOMTask -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromInstance
```
Get-SCOMTask [-Instance] <EnterpriseManagementObject[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCOMTask [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromTaskName
```
Get-SCOMTask [-Name <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCOMTask [-Target <ManagementPackClass[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMTask** cmdlet gets a list of tasks.
Use this cmdlet to get tasks that have a specific name or ID as well as tasks that are associated with specified user roles, class instances, management packs, or target classes.

## EXAMPLES

### Example 1: Get tasks by specifying a partial name
```
PS C:\>Get-SCOMTask -Name "*health*"
```

This command gets all tasks that have health in their names.

### Example 2: Get a task by using a partial display name
```
PS C:\>Get-SCOMTask -DisplayName "Stop*"
```

This command gets all tasks that have display names that begin with Stop.

### Example 3: Get a task by specifying a partial display name and an error action
```
PS C:\>Get-SCOMManagementPack -DisplayName "System Center Core*" | Get-SCOMTask -ErrorAction SilentlyContinue
```

This command gets all tasks for the management packs that have System Center Core in their display names.
The command uses the **Get-SCOMManagementPack** cmdlet to get management packs based on display names, and passes them to the to the **Get-SCOMTask** cmdlet.
Because the command specifies SilentlyContinue for the *ErrorAction* parameter, if the cmdlet finds a management pack with no associated tasks, it continues to run and does not display error messages.

### Example 4: Get tasks by using a partial class name
```
PS C:\>Get-SCOMClass -Name "*health*" | Get-SCOMTask
```

This command gets all tasks for classes that have health in their names.

### Example 5: Get tasks by specifying a partial class instance name
```
PS C:\>Get-SCOMClassInstance -Name "*.Contoso.com" | Get-SCOMTask
```

This command gets all tasks for class instances that have .Contoso.com in their names.

### Example 6: Get a task by specifying an ID
```
PS C:\>Get-SCOMTask -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the task that has an ID of 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

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
For more information about credential objects, type "`Get-Help Get-Credential`".

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

### -DisplayName
Specifies an array of display names for task objects.
This parameter takes one or more strings, and the cmdlet looks for matches among the display names of the task objects that the cmdlet works with.
Values for this parameter vary depending on which localized management packs are imported into the management group and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromTaskDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies an array of task IDs.
The cmdlet gets the tasks that have these IDs.
To obtain a task, use the **Get-SCOMTask** cmdlet.
The ID is the **ID** property of a task object.

```yaml
Type: Guid[]
Parameter Sets: FromTaskId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an array of **EnterpriseManagementObject** objects that represent class instances.
The cmdlet retrieves tasks for the class instances that the array stores.
Specify a variable that represents the class instances or use a cmdlet such as **Get-SCOMClassInstance** that gets the class instances.
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

### -ManagementPack
Specifies an array of management pack objects.
The cmdlet gets tasks for the management pack objects in the array.
Specify a variable that contains management pack objects, or use a cmdlet such as **Get-SCOMManagementPack** that gets management pack objects.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of task names.

The cmdlet takes each string in the array and matches it with the **Name** properties of the task objects that this cmdlet works with.

```yaml
Type: String[]
Parameter Sets: FromTaskName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter does not appear, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type "`Get-Help about_OpsMgr_Connections`".

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

### -Target
Specifies an array of management pack class objects that represent target classes.
Specify a variable that contains the target class objects, or use a cmdlet such as **Get-SCOMClass** that gets the target class objects.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMTaskResult](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMTaskResult.md)

[Start-SCOMTask](xref:SystemCenter2016/OperationsManager/vlatest/Start-SCOMTask.md)

