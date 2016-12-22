---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 662BB479-9F4B-48FB-8C2A-6E65593C0FBD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCUserRole

## SYNOPSIS
Modifies the settings for an existing VMM user role.

## SYNTAX

```
Set-SCUserRole [-UserRole <UserRole>] [-VMMServer <ServerConnection>] [-Name <String>] [-JobGroup <Guid>]
 [-AddMember <String[]>] [-RemoveMember <String[]>] [-Permission <SelfServicePermission[]>]
 [-UserRoleDataPath <String>] [-RemoveLibraryStoreSharePath] [-ShowPROTips <Boolean>]
 [-AddScope <ClientObject[]>] [-RemoveScope <ClientObject[]>] [-Description <String>]
 [-VMNetworkMaximum <UInt16>] [-VMNetworkMaximumPerUser <UInt16>] [-RemoveVMNetworkMaximum]
 [-RemoveVMNetworkMaximumPerUser] [-VPNConnectionMaximum <UInt16>] [-VPNConnectionMaximumPerUser <UInt16>]
 [-RemoveVPNConnectionMaximum] [-RemoveVPNConnectionMaximumPerUser] [-NATConnectionMaximum <UInt16>]
 [-NATConnectionMaximumPerUser <UInt16>] [-RemoveNATConnectionMaximum] [-RemoveNATConnectionMaximumPerUser]
 [-VMNetworkVPNMaximumBandwidthInKbps <UInt64>] [-VMNetworkVPNMaximumBandwidthOutKbps <UInt64>]
 [-RemoveVMNetworkVPNMaximumBandwidthIn] [-RemoveVMNetworkVPNMaximumBandwidthOut] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCUserRole** cmdlet modifies the settings for an existing Virtual Machine Manager (VMM) user role.
The settings that you can modify depend on the type of VMM user role.

The types of user roles are as follows:

VMM Administrator (Administrator)

You can add members to or remove members from the Administrator user role.
You cannot limit the scope of objects that members of this role can manage.

Delegated Administrator (DelegatedAdmin)

You can add members to and remove members from a Delegated Administrator user role.
You can expand or restrict the scope of a Delegated Administrator user role.
You can grant members of this user role permission to manage all of the objects in private clouds and host groups.
You can allow users to manage all of the objects stored on library servers.
Within that framework, you cannot limit the actions that members of the Delegated Administrator user role can perform.

Read-Only Administrator (ReadOnlyAdmin)

You can add members to and remove members from a Read-Only Administrator user role.
You can expand or restrict the scope of a Read-Only Administrator user role.
However, the members of the user role can only view the properties, status, and job status of the objects within their assigned scope.
They cannot modify any of the objects.

Self-Service User (SelfServiceUser)

You can add members to or remove members from a Self-Service user role.
You can expand or limit the scope and actions of members of a Self-Service user role.
You can grant members of a Self-Service user role permission to manage all of the objects in private clouds.
You can grant permission to create virtual machines, permission to store virtual machines in the stored virtual machine path in the cloud that the virtual machine is on, and permission to use template objects to create virtual machines.
Within that framework, you can grant members of a Self-Service user role actions that self-service users can take.
You can also limit the number of virtual machines that self-service users can create by setting a quota that applies to each user or to all users collectively. 

The actions that you can grant a self-service user include the following: 

- AllowLocalAdmin.
Grants user local administrator rights on virtual machines. 
- Author.
Author virtual machine and service templates.
- CanShare.
Share resources with other Self-Service users.
- CanReceive.
Receive resources from other Self-Service users.
- Checkpoint.
Create and manage virtual machine checkpoints.
- CheckpointRestoreOnly.
Can only restore a checkpoint.
- Create.
Create virtual machines and services from templates only.
- CreateFromVHDOrTemplate.
Create virtual machines and services from virtual hard disk (VHD) files or templates.
- PauseAndResume.
Pause and resume virtual machines and services.
- RemoteConnect.
Remotely connect to virtual machines.
- Remove.
Remove virtual machines and services.
- Save.
Save virtual machines and services.
- Shutdown.
Shut down virtual machines.
- Start.
Start virtual machines and services.
- Stop.
Stop virtual machines and services.
- Store.
Store virtual machines in a library.

## EXAMPLES

### Example 1: Add users to the VMM Administrator user role
```
PS C:\> $UserRole = Get-SCUserRole -Name "Administrator"
PS C:\> Set-SCUserRole -UserRole $UserRole -AddMember "Contoso\User01","Contoso\User02"
```

The first command gets the user role object named Administrator, and then stores that object in the $UserRole variable.

The second command adds User01 and User02 to the Administrator user role.
Both users are members of the Contoso.com domain.

### Example 2: Add users to the Administrator role by using the pipeline
```
PS C:\> Get-SCUserRole -VMMServer "VMMServer01.Contoso.com" | where { $_.Profile -eq "Administrator" } | Set-SCUserRole -AddMember "Contoso\User03"
```

This command gets all user role objects from VMMServer01, selects the user role objects whose profile is Administrator, and then adds User03 to the Administrator user role.

### Example 3: Modify an existing Self-Service user role by adding a cloud to its scope
```
PS C:\> $Cloud = Get-SCCloud -Name "Cloud02"
PS C:\> $UserRole = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> Set-SCUserRole -UserRole $UserRole -AddScope $Cloud
```

The first command gets the cloud object named Cloud02, and then stores that object in the $Cloud variable.

The second command gets the user role object named ContosoSelfServiceUsers, and then stores the object in the $UserRole profile.

The last command modifies the scope of the user role stored in $UserRole by adding the cloud stored in $Cloud to its scope.

### Example 4: Remove the specified user from the Administrator user role
```
PS C:\> $UserRole = Get-SCUserRole -Name "Administrator"
PS C:\> Set-SCUserRole -UserRole $UserRole -RemoveMember "Contoso\User01"
```

The first command gets the user role object named Administrator, and then stores that object in the $UserRole variable.

The second command removes User01 from the Administrator user role.
User01 is a member of the Contoso.com domain.

### Example 5: Add a cloud to the scope of a Self-Service user role
```
PS C:\> $Cloud = Get-SCCloud -Name "Cloud03"
PS C:\> Get-SCUserRole -Name "ContosoSelfServiceUsers" | Set-SCUserRole -AddScope $Cloud
```

The first command gets the cloud object named Cloud03, and then stores that object in the $Cloud variable.

The second command gets the user role object named ContosoSelfServiceUsers, and then passes that user role object to the current cmdlet.
This cmdlet adds the cloud stored in $Cloud to the user role.

### Example 6: Modify what actions members of a Self-Service user role can take on their virtual machines
```
PS C:\> $UserRole = Get-SCUserRole -VMMServer "VMMServer01.Contoso.com" -Name "ContosoSelfServiceUsers"
PS C:\> Set-SCUserRole -UserRole $UserRole -Permission "Create,PauseAndResume,Stop,AllowLocalAdmin,Store"
```

The first command gets the user role object on VMMServer01 named ContosoSelfServiceUsers, and then stores the object in the $UserRole variable.

The second command modifies the permissions for members of the user role stored in $UserRole to allow Creation, PauseAndResume, Stop, AllowLocalAdmin, and Store permissions.

## PARAMETERS

### -AddMember
Specifies an array of members that this cmdlet adds to an object that has the concept of members, such as a group.
For example, this cmdlet can add one or more Active Directory® Domain Services domain users or groups to a user role.
Specify members in the following formats: 

- Domain\User
- User
- User@Domain
- Domain\LabGroupAlias
- LabGroupAlias

The lab group alias is an Active Directory Domain Services security group, not an e-mail alias.

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

### -AddScope
Specifies an array of scopes that this cmdlet adds to the scope of objects that members of this user role can manage.

```yaml
Type: ClientObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the user role.

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

### -JobGroup
Specifies an identifier for a series of commands that runs as a set just before the final command that includes the same job group identifier runs.

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

### -NATConnectionMaximum


```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NATConnectionMaximumPerUser


```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a new name for the user role.

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

### -Permission
Specifies an array of actions that members of a Self-Service user role can perform on their virtual machines or services.
Valid values are: 

- AllowLocalAdmin 
- Author 
- CanShare 
- CanReceive 
- Checkpoint 
- CheckpointRestoreOnly 
- Create 
- CreateFromVHDOrTemplate 
- PauseAndResume 
- RemoteConnect 
- Remove 
- Save 
- Shutdown 
- Start 
- Stop 
- Store 

If you grant the CreateFromVHDOrTemplate permission, you also grant the Create permission.
If you grant the Checkpoint permission, you also grant CheckpointRestoreOnly permission.

```yaml
Type: SelfServicePermission[]
Parameter Sets: (All)
Aliases: VMPermission
Accepted values: Create, PauseAndResume, Start, Stop, AllowLocalAdmin, RemoteConnect, Remove, Shutdown, Checkpoint, Store, Save, Author, CanShare, CanReceive, CreateFromVHDOrTemplate, CheckpointRestoreOnly, AuthorVMNetwork, CreateShielded

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveLibraryStoreSharePath
Indicates that this cmdlet clears the user role data path for a self-service user.

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

### -RemoveMember
Specifies an array of members that this cmdlet removes from a VMM object that has the concept of membership, such as a group.
For example, this cmdlet can removes one or more Active Directory Domain Services domain users or groups from a user role.
Specify members in the following formats: 

- Domain\User
- User
- User@Domain
- Domain\LabGroupAlias
- LabGroupAlias

The lab group alias is an Active Directory Domain Services security group, not an e-mail alias.

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

### -RemoveNATConnectionMaximum


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

### -RemoveNATConnectionMaximumPerUser


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

### -RemoveScope
Specifies an array of VMM objects to remove from the scope of objects that members of this user role can manage.

```yaml
Type: ClientObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveVMNetworkMaximum
Indicates that this cmdlet removes the virtual machine network maximum setting.

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

### -RemoveVMNetworkMaximumPerUser
Indicates that this cmdlet removes the virtual machine network maximum per user setting.

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

### -RemoveVMNetworkVPNMaximumBandwidthIn
Indicates that this cmdlet removes the virtual private network (VPN) maximum bandwidth setting for incoming connections.

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

### -RemoveVMNetworkVPNMaximumBandwidthOut
Indicates that this cmdlet removes the VPN maximum bandwidth setting for outgoing connections.

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

### -RemoveVPNConnectionMaximum
Indicates that this cmdlet removes the VPN connection maximum setting.

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

### -RemoveVPNConnectionMaximumPerUser
Indicates that this cmdlet removes the VPN connection maximum per user setting.

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

### -ShowPROTips
Indicates whether to show PRO tips.
This parameter only applies to Self-Service user roles.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object that this cmdlet modifies.
To obtain a user role, use the **Get-SCUserRole** cmdlet.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UserRoleDataPath
Specifies the path of a library share that members of a Self-Service user role can use to upload data.
Specify the path in this format: \\\\LibraryServerName\LibraryShareName.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LibraryStoreSharePath

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies the VMM server on which this cmdlet modifies a user role.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkMaximum
Specifies the maximum number of virtual machine networks for a user role.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkMaximumPerUser
Specifies the maximum number of virtual machine networks for a user.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkVPNMaximumBandwidthInKbps
Specifies the maximum bandwidth, kilobits per second, for incoming traffic for a VPN.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworkVPNMaximumBandwidthOutKbps
Specifies the maximum bandwidth, kilobits per second, for outgoing traffic for a VPN.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VPNConnectionMaximum
Specifies the maximum number of connections for a VPN.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VPNConnectionMaximumPerUser
Specifies the maximum number of connections per user for a VPN.

```yaml
Type: UInt16
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

### UserRole

## NOTES
* To list all available permissions that you can specify for self-service users, type the following command: 

`PS C:\\\> \[enum\]::GetValues(\[Microsoft.VirtualManager.Remoting.SelfServicePermission\])`

  

## RELATED LINKS

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Grant-SCResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCResource.md)

[New-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCUserRole.md)

[Remove-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUserRole.md)

[Revoke-SCResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCResource.md)

