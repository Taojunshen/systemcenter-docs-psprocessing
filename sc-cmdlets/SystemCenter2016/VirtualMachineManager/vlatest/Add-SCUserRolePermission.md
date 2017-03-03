---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A0F64A39-E20E-4894-B9F3-F320383272F1
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUserRolePermission.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUserRolePermission.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUserRolePermission.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCUserRolePermission

## SYNOPSIS
Adds a permission to a user role.

## SYNTAX

### Values
```
Add-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRole <SelfServiceUserRole> -Cloud <Cloud>
 [-AllowLocalAdmin] [-Checkpoint] [-CheckpointRestoreOnly] [-DeployFromTemplateOnly] [-Deploy]
 [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start] [-Stop] [-Store] [-DeployShielded]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UserRole
```
Add-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRole <SelfServiceUserRole> [-AllowLocalAdmin]
 [-Author] [-AuthorVMNetwork] [-CanShare] [-CanReceive] [-Checkpoint] [-CheckpointRestoreOnly]
 [-DeployFromTemplateOnly] [-Deploy] [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start]
 [-Stop] [-Store] [-DeployShielded] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### JobGroup
```
Add-SCUserRolePermission [-VMMServer <ServerConnection>] [-Cloud <Cloud>] -JobGroup <Guid> [-AllowLocalAdmin]
 [-Author] [-AuthorVMNetwork] [-CanShare] [-CanReceive] [-Checkpoint] [-CheckpointRestoreOnly]
 [-DeployFromTemplateOnly] [-Deploy] [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start]
 [-Stop] [-Store] [-DeployShielded] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UserRolePermission
```
Add-SCUserRolePermission [-VMMServer <ServerConnection>] -UserRolePermission <UserRolePermission>
 [-AllowLocalAdmin] [-Checkpoint] [-CheckpointRestoreOnly] [-DeployFromTemplateOnly] [-Deploy]
 [-PauseAndResume] [-RemoteConnect] [-Remove] [-Save] [-Shutdown] [-Start] [-Stop] [-Store] [-DeployShielded]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCUserRolePermission** cmdlet grants a permission to a user role.

## EXAMPLES


## PARAMETERS

### -AllowLocalAdmin
Indicates that this cmdlet grants the Allow Local Admin permission.

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
Indicates that this cmdlet grants the Author permission.

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
Indicates that this cmdlet grants the Author VMNetwork permission.

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
Indicates that this cmdlet grants the Can Receive permission.

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
Indicates that this cmdlet grants the Can Share permission.

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
Indicates that this cmdlet grants the Can Checkpoint permission.

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
Indicates that this cmdlet grants the Can Checkpoint Restore Only permission.

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
Indicates that this cmdlet grants the Deploy virtual machine permission.

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
Indicates that this cmdlet grants the Deploy From Template Only virtual machine permission.

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
Indicates that this cmdlet grants the Deploy Shielded permission.

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
Indicates that this cmdlet grants the Can Pause And Resume permission.

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
Indicates that this cmdlet grants the Remote Connect permission.

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
Indicates that this cmdlet grants the Can Remove permission.

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
Indicates that this cmdlet grants the Can Save VM permission.

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
Indicates that this cmdlet grants the Can Shutdown virtual machine permission.

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
Indicates that this cmdlet grants the Can Start virtual machine permission.

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
Indicates that this cmdlet grants the Can Stop virtual machine permission.

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
Indicates that this cmdlet grants the Can Store virtual machine permission.

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
Specifies a user role to which this cmdlet adds permissions.

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
Specifies a **UserRolePermission** to which this cmdlet adds permissions.
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
Specifies a Virtual Machine Manager (VMM) server on which this cmdlet modifies a user role.

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

### UserRole
This cmdlet returns a **UserRole** object.

## NOTES

## RELATED LINKS

[Get-SCUserRolePermission](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRolePermission.md)

[Remove-SCUserRolePermission](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRolePermission.md)

