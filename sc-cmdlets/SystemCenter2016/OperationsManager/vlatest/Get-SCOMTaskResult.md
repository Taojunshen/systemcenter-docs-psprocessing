---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CA42319F-D9AB-4EB0-B43C-9287AABD8572
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTaskResult.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTaskResult.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMTaskResult.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMTaskResult

## SYNOPSIS
Gets the results for tasks that have run.

## SYNTAX

### Empty (Default)
```
Get-SCOMTaskResult [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromTaskResultBatchId
```
Get-SCOMTaskResult [-BatchID] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromTaskResultId
```
Get-SCOMTaskResult [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromInstance
```
Get-SCOMTaskResult [-Instance] <EnterpriseManagementObject[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromTask
```
Get-SCOMTaskResult [-Task] <ManagementPackTask[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMTaskResult** cmdlet gets the results for tasks that have run.
Use this cmdlet to get results by task name or ID as well as for tasks that are associated with specified class instances or batches.

## EXAMPLES

### Example 1: Get task results by specifying a partial display name and an error action
```
PS C:\>Get-SCOMTask -Name "*SystemCenter*" | Get-SCOMTaskResult -ErrorAction SilentlyContinue
```

This command gets results for tasks that have SystemCenter in their names.
The command uses the **Get-SCOMTask** cmdlet to get tasks based on name and passes them to the **Get-SCOMTaskResult** cmdlet by using the pipeline operator.
Because the command specifies SilentlyContinue for the *ErrorAction* parameter, if the cmdlet finds a task with no matching results, the command continues to run and does not display error messages.

### Example 2: Get task results by specifying class instances
```
PS C:\>Get-SCOMClassInstance -DisplayName "*.Consoso.com" | Get-SCOMTaskResult -ErrorAction SilentlyContinue
```

This command gets all class instances in the Contoso.com domain and then returns the task results for each class instance object.
The command uses the **Get-SCOMClassInstance** cmdlet to get all the instances that have a display name that contains .Contoso.com and passes them to the **Get-SCOMTaskResult** cmdlet by using the pipeline operator.
Because the command specifies SilentlyContinue for the *ErrorAction* parameter, if the cmdlet finds a class instance with no matching task results, the command continues to run and does not display error messages.

### Example 3: Get task results by specifying a task ID
```
PS C:\>Get-SCOMTaskResult -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the results of the task that has an ID of 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

### Example 4: Get task results by specifying a batch ID
```
PS C:\>Get-SCOMTaskResult -BatchId 2ef74789-f9f5-46b0-af70-16d01d4f4577
```

This command gets the results of a task that runs in a batch that has an ID of 2ef74789-f9f5-46b0-af70-16d01d4f4577.

## PARAMETERS

### -BatchID
Specifies an array that contains the IDs of batches in which tasks run.
The cmdlet gets task results for each batch.

```yaml
Type: Guid[]
Parameter Sets: FromTaskResultBatchId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array that contains the name of the computer with which to establish a connection.
Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, specify the computer name,  localhost, or a dot (.).

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
Specifies an array of task IDs.
The cmdlet gets the results of tasks that have these IDs.

```yaml
Type: Guid[]
Parameter Sets: FromTaskResultId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an array of class instances for which to start a task.
Specify a variable that stores class instances, or use a cmdlet such as **Get-SCOMClassInstance** that gets the class instances.
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

### -SCSession
Specifies an array of connections to management servers.
To obtain management group connection objects, use the **Get-SCOMManagementGroupConnection** cmdlet.
If this parameter does not appear, the default is the current management group connection.

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

### -Task
Specifies an array of management pack tasks.
The cmdlet gets results for the task objects that the array contains.
Specify a variable that contains task objects or use a cmdlet such as **Get-SCOMTask** cmdlet that gets tasks.

```yaml
Type: ManagementPackTask[]
Parameter Sets: FromTask
Aliases: 

Required: True
Position: 1
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

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

[Get-SCOMTask](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMTask.md)

[Start-SCOMTask](xref:SystemCenter2016/OperationsManager/vlatest/Start-SCOMTask.md)

