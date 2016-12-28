---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 983712D8-386F-460B-8E00-1240543CE7CE
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRolePermission.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRolePermission.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRolePermission.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCUserRolePermission

## SYNOPSIS
Removes a permission from a user role.

## SYNTAX

### Values
```
Remove-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRole <SelfServiceUserRole> -Cloud <Cloud>
 [-AllowLocalAdmin] [-Checkpoint] [-CheckpointRestoreOnly] [-DeployFromTemplateOnly] [-Deploy]
 [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start] [-Stop] [-Store] [-DeployShielded]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UserRole
```
Remove-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRole <SelfServiceUserRole> [-AllowLocalAdmin]
 [-Author] [-AuthorVMNetwork] [-CanShare] [-CanReceive] [-Checkpoint] [-CheckpointRestoreOnly]
 [-DeployFromTemplateOnly] [-Deploy] [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start]
 [-Stop] [-Store] [-DeployShielded] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### JobGroup
```
Remove-SCUserRolePermission [-VMMServer <ServerConnection>] [-Cloud <Cloud>] -JobGroup <Guid>
 [-AllowLocalAdmin] [-Author] [-AuthorVMNetwork] [-CanShare] [-CanReceive] [-Checkpoint]
 [-CheckpointRestoreOnly] [-DeployFromTemplateOnly] [-Deploy] [-PauseAndResume] [-RemoteConnect] [-Remove]
 [-Save] [-Shutdown] [-Start] [-Stop] [-Store] [-DeployShielded] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UserRolePermission
```
Remove-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRolePermission <UserRolePermission>
 [-AllowLocalAdmin] [-Checkpoint] [-CheckpointRestoreOnly] [-DeployFromTemplateOnly] [-Deploy]
 [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start] [-Stop] [-Store] [-DeployShielded]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCUserRolePermission** cmdlet removes a permission from a user role.

## EXAMPLES


## PARAMETERS

### -AllowLocalAdmin
Indicates that this cmdlet removes the Allow Local Admin permission.

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

### -Author
Indicates that this cmdlet removes the Author permission.

```yaml
Type: SwitchParameter
Parameter Sets: UserRole, JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthorVMNetwork
Indicates that this cmdlet removes the Author VMNetwork permission.

```yaml
Type: SwitchParameter
Parameter Sets: UserRole, JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CanReceive
Indicates that this cmdlet removes the Can Receive permission.

```yaml
Type: SwitchParameter
Parameter Sets: UserRole, JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CanShare
Indicates that this cmdlet removes the Can Share permission.

```yaml
Type: SwitchParameter
Parameter Sets: UserRole, JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Checkpoint
Indicates that this cmdlet removes the Can Checkpoint permission.

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

### -CheckpointRestoreOnly
Indicates that this cmdlet removes the Can Checkpoint Restore Only permission.

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

### -Cloud
Specifies a private cloud object for which this cmdlet modifies a user role.

```yaml
Type: Cloud
Parameter Sets: Values
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Cloud
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deploy
Indicates that this cmdlet removes the Deploy virtual machine permission.

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

### -DeployFromTemplateOnly
Indicates that this cmdlet removes the Deploy From Template Only virtual machine permission.

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

### -DeployShielded
Indicates that this cmdlet removes the Deploy Shielded permission.

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

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

```yaml
Type: Guid
Parameter Sets: JobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PauseAndResume
Indicates that this cmdlet removes the Can Pause And Resume permission.

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

### -RemoteConnect
Indicates that this cmdlet removes the Remote Connect permission.

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

### -Remove
Indicates that this cmdlet removes the Can Remove permission.

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

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -Save
Indicates that this cmdlet removes the Can Save VM permission.

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

### -Shutdown
Indicates that this cmdlet removes the Can Shutdown virtual machine permission.

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

### -Start
Indicates that this cmdlet removes the Can Start virtual machine permission.

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

### -Stop
Indicates that this cmdlet removes the Can Stop virtual machine permission.

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

### -Store
Indicates that this cmdlet removes the Can Store virtual machine permission.

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

### -UserRole
Specifies a user role from which this cmdlet removes permissions.

```yaml
Type: SelfServiceUserRole
Parameter Sets: Values, UserRole
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserRolePermission
Specifies a **UserRolePermission** from which this cmdlet removes permissions.
To obtain a user role permission, use the **Get-SCUserRolePermission** cmdlet.

```yaml
Type: UserRolePermission
Parameter Sets: UserRolePermission
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server on which this cmdlet removes permissions.

```yaml
Type: ServerConnection
Parameter Sets: (All)
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

[Add-SCUserRolePermission](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUserRolePermission.md)

[Get-SCUserRolePermission](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRolePermission.md)

