---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1C397C9C-4D0B-4FD2-88F7-1F7475ED785B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRoleQuota.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRoleQuota.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRoleQuota.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCUserRoleQuota

## SYNOPSIS
Gets a user role quota.

## SYNTAX

```
Get-SCUserRoleQuota [-VMMServer <ServerConnection>] [[-UserRole] <UserRole>] [-QuotaPerUser <Boolean>]
 [-Cloud <Cloud>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCUserRoleQuota** cmdlet gets Virtual Machine Manager (VMM) user role quota objects.

This cmdlet returns two user role quota objects for a self-service user role per private cloud.
One object contains information about the role-level quota.
The other object contains information about member-level quota.
Specify a value of $True for the QuotaPerUser cmdlet to return only the member-level quota object.
Specify a value of $False for the cmdlet to return only the role-level quota object.

## EXAMPLES

### Example 1: Get per-user virtual machine count quota
```
PS C:\> $Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $Role = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> $Quota = Get-SCUserRoleQuota -Cloud $Cloud -UserRole $Role -QuotaPerUser $True
PS C:\> Write-Output $Quota.VMCount
```

The first command gets the private cloud object named Cloud01, and then stores that object in the $Cloud variable.

The second command gets the user role object named ContosoSelfServiceUsers, and then stores that object in the $Role variable.

The third command gets the user role quota for the private cloud stored in $Cloud and user role stored in $Role.
Because the *QuotaPerUser* parameter has a value of $True, this command gets the quota for members.

The last command displays the virtual machine count quota.

## PARAMETERS

### -Cloud
Specifies a private cloud object in which this cmdlet gets user role quotas.

```yaml
Type: Cloud
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

### -QuotaPerUser
Indicates whether this cmdlet gets user level quotas or member level quotas.
Specify a value of $True to get member level quotas.
Specify a value of $False to get role level quotas.
If you do not specify this parameter, the cmdlet returns both types of quotas.

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
Specifies a user role object for which this cmdlet gets user role quotas.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object on which this cmdlet gets user role quotas.

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

### UserRoleQuota
This cmdlet returns a **UserRoleQuota** object.

## NOTES

## RELATED LINKS

[Get-SCCloud](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCloud.md)

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Set-SCUserRoleQuota](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUserRoleQuota.md)

