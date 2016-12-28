---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 819FCBE8-746E-450E-AA7C-0039C6231398
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRoleQuota.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRoleQuota.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRoleQuota.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCUserRoleQuota

## SYNOPSIS
Modifies the settings for a user role quota.

## SYNTAX

### JobGroup
```
Set-SCUserRoleQuota [-VMMServer <ServerConnection>] -JobGroup <Guid> -Cloud <Cloud> [-CPUCount <Int32>]
 [-CustomQuotaCount <Int32>] [-MemoryMB <Int32>] [-StorageGB <Int32>] [-VMCount <Int32>] [-UseCPUCountMaximum]
 [-UseCustomQuotaCountMaximum] [-UseMaximumQuota] [-UseMemoryMBMaximum] [-UseStorageGBMaximum]
 [-UseVMCountMaximum] [-QuotaPerUser] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UseDefault
```
Set-SCUserRoleQuota [-VMMServer <ServerConnection>] [-UserRoleQuota <UserRoleQuota>] [-UseMaximumQuota]
 [-QuotaPerUser] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Values
```
Set-SCUserRoleQuota [-VMMServer <ServerConnection>] -UserRoleQuota <UserRoleQuota> [-CPUCount <Int32>]
 [-CustomQuotaCount <Int32>] [-MemoryMB <Int32>] [-StorageGB <Int32>] [-VMCount <Int32>] [-UseCPUCountMaximum]
 [-UseCustomQuotaCountMaximum] [-UseMemoryMBMaximum] [-UseStorageGBMaximum] [-UseVMCountMaximum]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCUserRoleQuota** cmdlet modifies the settings for a Virtual Machine Manager (VMM) user role quota.

## EXAMPLES

### Example 1: Increase virtual machine count quota
```
PS C:\> $Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $Role = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> $Quota = Get-SCUserRoleQuota -Cloud $Cloud -UserRole $Role -QuotaPerUser $False
PS C:\> Write-Output $Quota.VMCount
PS C:\> if ($Quota.VMCount -lt 20) {Set-SCUserRoleQuota -UserRoleQuota $Quota -VMCount 20}
```

The first command gets the cloud named Cloud01, and then stores that object in the $Cloud variable.

The second command gets the user role named ContosoSelfServiceUsers, and then stores that object in the $Role variable.

The third command gets the user role quota for the cloud stored in $Cloud and user role stored in $Role.
Because the *QuotaPerUser* parameter has a value of $False, the command gets the quota for the user role.

The fourth command displays the virtual machine count quota.

The final command determines whether the virtual machine quota is less than 20.
If it is, then it sets the quota to 20.

## PARAMETERS

### -CPUCount
Specifies the number of virtual CPUs for a user role quota.

```yaml
Type: Int32
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cloud
Specifies a private cloud object in which this cmdlet modifies user role quotas.

```yaml
Type: Cloud
Parameter Sets: JobGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomQuotaCount
Specifies the number of custom quota points for a user role quota.

```yaml
Type: Int32
Parameter Sets: JobGroup, Values
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

### -MemoryMB
Specifies the amount of memory, in megabytes (MB), for a user role quota.

```yaml
Type: Int32
Parameter Sets: JobGroup, Values
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

### -QuotaPerUser
Indicates that this sets member level quotas.
Specifying $False indicates role level quotas.
If the parameter is not used, both quotas are set or returned.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, UseDefault
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

### -StorageGB
Specifies the amount of storage, in gigabytes (GB), for a user role quota.
This storage amount does not include library storage.

```yaml
Type: Int32
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCPUCountMaximum
Indicates that the maximum number of virtual CPUs is allowed for a user role.
If you specify this parameter, VMM does not enforce a user role quota for the virtual CPU dimension.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseCustomQuotaCountMaximum
Indicates that the maximum number of custom quota points is allowed for a user role.
If you specify this parameter, VMM does not enforce a user role quota for the custom quota dimension.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMaximumQuota
Indicates that all quota dimensions are set to maximum.
If you specify this parameter, VMM does not enforce user role quotas.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: UseDefault
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseMemoryMBMaximum
Indicates that the maximum amount of memory, in megabytes, is allowed for a user role.
If you specify this parameter, VMM does not enforce a user role quota for the memory dimension.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseStorageGBMaximum
Indicates that the maximum amount of storage, in gigabytes, is allowed for a user role.
If you specify this parameter, VMM does not enforce a user role quota for the storage dimension.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseVMCountMaximum
Indicates that the maximum number of virtual machines is allowed for a user role.
If you specify parameter, VMM does not enforce a user role quota for the virtual machine dimension.

```yaml
Type: SwitchParameter
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRoleQuota
Specifies a user role quota object.

```yaml
Type: UserRoleQuota
Parameter Sets: UseDefault
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: UserRoleQuota
Parameter Sets: Values
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMCount
Specifies the number of virtual machines for a user role quota.

```yaml
Type: Int32
Parameter Sets: JobGroup, Values
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server on which this cmdlet modifies a user role quota.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### UserRoleQuota
This cmdlet returns a **UserRoleQuota** object.

## NOTES

## RELATED LINKS

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Get-SCUserRoleQuota](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRoleQuota.md)

