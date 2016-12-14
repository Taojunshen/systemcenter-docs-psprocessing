---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187715
schema: 2.0.0
ms.assetid: 311E8DF5-9890-40B6-B8B4-7F5CA6D68EB3
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Start-SCOMTask.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Start-SCOMTask.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Start-SCOMTask.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCOMTask

## SYNOPSIS
Starts a task for a specified object.

## SYNTAX

```
Start-SCOMTask [-Instance] <EnterpriseManagementObject[]> [-Task] <ManagementPackTask>
 [[-TaskCredentials] <PSCredential>] [[-Override] <Hashtable>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCOMTask** cmdlet starts a task for a specified object.
This cmdlet takes a task object and a class instance object as input.
The cmdlet accepts only one task, but it can accept multiple class instances and overrides.

## EXAMPLES

### Example 1: Start a task by using a display name
```
PS C:\>$Instances = Get-SCOMClassInstance -Name "*.Contoso.com"
PS C:\> Get-SCOMTask -DisplayName "Get Monitor State" | Start-SCOMTask -Instance $Instances
```

This example starts a task by using a display name.

The first command gets all class instances in the Contoso.com domain and stores them in the $Instances variable.

The second command gets the task that has the display name Get Monitor State and starts the task for each class instance that is stored in the $Instances variable.

### Example 2: Start a task by using a display name and a timeout specification
```
PS C:\>$Overrides = @{Timeout=60}
PS C:\> $Instances = Get-SCOMClassInstance -DisplayName "Contoso Service"
PS C:\> $Task = Get-SCOMTask -DisplayName "Start NT Service"
PS C:\> Start-SCOMTask -Task $Task -Instance $Instances -Override $Overrides
```

This example shows how to start a task by using a display name and a hash table that specifies a timeout value.

The first command creates a hash table that has a value for the Timeout key and stores it in the $Overrides variable.

The second command gets all class instances that have the name Contoso Service and stores them in the $Instances variable.

The third command gets the task that has the display name Start NT Service and starts the task for each class instance that is stored in the $Instances variable.

The fourth command starts the task for each class instance that is stored in the $Instances variable.
The command specifies a Timeout key value of 60.

### Example 3: Start a task by using credentials
```
PS C:\>$Credential = Get-Credential
PS C:\> $Instance = Get-SCOMClassInstance -Name "Server01.Contoso.com"
PS C:\> Get-SCOMTask -DisplayName "Reset State" | Start-SCOMTask -Instance $Instance -TaskCredentials $Credential
```

This example starts a task by using credentials.

The first command prompts the user for a user name and password, creates a credential object from the input, and stores the credential object in the $Credential variable.

The second command gets a class instance named Server01.Contoso.com and stores it in the $Instance variable.

The third command gets a task that has the display name Reset State and starts the task for the class instance that is stored in $Instance.
The command runs the task under the credentials that are stored in $Credential.

## PARAMETERS

### -Instance
Specifies an array of **EnterpriseManagementObject** objects that represent class instance objects for which to start a task.
Specify a variable that stores the class instances or use a cmdlet such as the **Get-SCOMClassInstance** cmdlet that gets the class instances.
This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Override
Specifies a hash table that defines new values for one or more task parameters, if those parameters allow overrides.
For more information about hash tables, type "`Get-Help about_Hash_Tables`".

To determine which parameters for a task allow overrides, use the **GetOverrideableParameters** method for the task object.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Task
Specifies a task object to start.
Specify a variable that represents a task, or use a cmdlet such as the **Get-SCOMTask** cmdlet that gets a task.
This parameter accepts only one task object.

```yaml
Type: ManagementPackTask
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskCredentials
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
Position: 3
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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMGroup.md)

[Get-SCOMTask](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMTask.md)

[Get-SCOMTaskResult](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMTaskResult.md)

