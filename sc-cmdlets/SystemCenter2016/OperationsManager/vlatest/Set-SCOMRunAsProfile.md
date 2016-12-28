---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B9AE75E4-E878-4F25-93F3-DF4D91E247C8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMRunAsProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMRunAsProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMRunAsProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMRunAsProfile

## SYNOPSIS
Adds Run As accounts to or removes them from a Run As profile.

## SYNTAX

### Empty (Default)
```
Set-SCOMRunAsProfile [-Account] <SecureData[]> [-Profile] <ManagementPackSecureReference>
 [-Action] <RunAsProfileAccountsAction> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackClass
```
Set-SCOMRunAsProfile [-Class] <ManagementPackClass[]> [-Account] <SecureData[]>
 [-Profile] <ManagementPackSecureReference> [-Action] <RunAsProfileAccountsAction> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromInstance
```
Set-SCOMRunAsProfile [-Instance] <MonitoringObject[]> [-Account] <SecureData[]>
 [-Profile] <ManagementPackSecureReference> [-Action] <RunAsProfileAccountsAction> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### FromGroup
```
Set-SCOMRunAsProfile [-Group] <MonitoringObject[]> [-Account] <SecureData[]>
 [-Profile] <ManagementPackSecureReference> [-Action] <RunAsProfileAccountsAction> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMRunAsProfile** cmdlet adds Run As accounts to or removes Run As accounts from a Run As profile.

## EXAMPLES

### Example 1: Add a Run As account to a Run As profile by specifying an account name
```
PS C:\>$Profile = Get-RunAsProfile -DisplayName "Privileged Monitoring Account"
PS C:\> $Account = Get-SCOMRunAsAccount -Name "High Privileged Account"
PS C:\> Set-SCOMRunAsProfile -Action "Add" -Profile $Profile -Account $Account
```

This example adds a Run As account to a Run As profile by specifying an account name.

The first command gets the Run As profile that has the display name Privileged Monitoring Account and stores it in the $Profile variable.

The second command gets the Run As account named High Privileged Account and stores it in the $Account variable.

The third command adds the account stored in the $Account variable to the Run As profile stored in the $Profile variable and configures the Run As account.
Because the command does not specify a class, group or object, it configures the Run As account to manage all targeted objects.

### Example 2: Add a Run As account to a Run As profile by specifying a path
```
PS C:\>$Profile = Get-SCOMRunAsProfile -DisplayName "SQL Server Monitoring Account"
PS C:\> $Account = Get-SCOMrunAsAccount -Name "Contoso\SQLAuth"
PS C:\> $Group = Get-SCOMGroup -DisplayName "Contoso financial SQL Servers"
PS C:\> Set-SCOMRunAsProfile -Action "Add" -Profile $Profile -Account $Account -Group $Group
```

This example adds a Run As account to a Run As profile by specifying a path name.

The first command gets the Run As profile named SQL Server Monitoring Account and stores it in the $Profile variable.

The second command gets the Run As account named Contoso\SQLAuth and stores it in the $Account variable.

The third command gets the group named Contoso financial SQL Servers and stores it in the $Group variable.

The fourth command adds the account stored in the $Account variable to the Run As profile stored in the $Profile variable and configures the Run As account to manage the group stored in the $Group variable.

### Example 3: Add a Run As account to a Run As profile by specifying an object
```
PS C:\>$Profile = Get-SCOMRunAsProfile -DisplayName "SQL Server Monitoring Account"
PS C:\> $Account = Get-SCOMrunAsAccount -Name "Contoso\SQLAuth"
PS C:\> $Group = Get-SCOMGroup -DisplayName "Contoso financial SQL Servers"
PS C:\> Set-SCOMRunAsProfile -Action "Add" -Profile $Profile -Account $Account -Group $Group
```

This example adds a Run As account to a Run As profile by specifying an account object.

The first command gets the Run As profile object that has the display name SQL Server Monitoring Account and stores the object in the $Profile variable.

The second command gets the Run As account object named Contoso\SQLAuth and stores the object in the $Account variable.

The third command gets the group object that has the display name Contoso financial SQL Servers and stores the object in the $Group variable.

The last command adds the account and group stored in $Account and $Group to the profile SQL Server Monitoring Account, which is stored in the $Profile variable.

## PARAMETERS

### -Account
Specifies an array of **Microsoft.EnterpriseManagement.Security.SecureData** objects that represent Run As accounts.
To obtain a **SecureData** object, use the **Get-SCOMRunAsAccount** cmdlet.

```yaml
Type: SecureData[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Action
Specifies the action to take to update the Run As profile.
The acceptable values for this parameter are: Add or Remove.

```yaml
Type: RunAsProfileAccountsAction
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Class
Specifies an array of **ManagementPackClass** objects that represent the classes that the Run As account can manage.
Specify a variable that stores classes, or use a cmdlet such as **Get-SCOMClass** that gets classes.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies an array of monitoring objects that represent the groups that the Run As account can manage.
Specify a variable that stores groups, or use a cmdlet such as **Get-SCOMGroup** that gets groups.

```yaml
Type: MonitoringObject[]
Parameter Sets: FromGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent the class instances that the Run As account can manage.
Specify a variable that stores class instances, or use a cmdlet such as **Get-SCOMClassInstance** that gets class instances.
This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: MonitoringObject[]
Parameter Sets: FromInstance
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profile
Specifies the Run As profile to update.
Specify a variable that stores a Run As profile, or use a cmdlet such as **Get-SCOMRunAsProfile** that gets a profile.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
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

[Add-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsProfile.md)

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Get-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsProfile.md)

[Remove-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsProfile.md)

