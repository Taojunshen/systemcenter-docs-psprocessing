---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCloud.md
schema: 2.0.0
ms.assetid: D806BACA-E9EB-4945-AA6C-CF5F56BA4B42
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCloudUsage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCloudUsage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCCloudUsage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCloudUsage

## SYNOPSIS
Gets cloud usage data for a specified private cloud in VMM.

## SYNTAX

### CloudUsage (Default)
```
Get-SCCloudUsage [-VMMServer <ServerConnection>] -Cloud <Cloud> [-ReturnPerUserRole] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### UserRoleUsageOfCloud
```
Get-SCCloudUsage [-VMMServer <ServerConnection>] -Cloud <Cloud> -UserRole <UserRole> [-UserName <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCloudUsage** cmdlet gets cloud usage data for a specified private cloud in Virtual Machine Manager (VMM).
Cloud usage data includes the following: 

- Number of CPUs
- Custom quota points
- Amount of memory (in MB) 
- Amount of storage (in GB) 
- Number of Virtual Machines

 You can scope this data to usage per user role and per user.

## EXAMPLES

### Example 1: Get the usage information for a specified private cloud
```
PS C:\>$Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> Get-SCCloudUsage -Cloud $Cloud
```

The first command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The second command gets the cloud usage information for the private cloud stored in $Cloud and displays the following information to the user: 

- CPUUsageCount
- CustomQuotaUsageCount
- MemoryUsageMB
- StorageUsageGB
- VMUsageCount

### Example 2: Get the usage information for a specified private cloud for a specified user role
```
PS C:\>$Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $UserRole = Get-SCUserRole -Name "SelfServiceUsers"
PS C:\> Get-SCCloudUsage -Cloud $Cloud -UserRole $UserRole
```

The first command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The second command gets the user role object named SelfServiceUsers and stores the object in the $UserRole variable.

The last command gets the cloud usage information for the private cloud stored in $Cloud and the user role stored in $UserRole.
Then, the command displays the cloud usage information to the user.

### Example 3: Get the usage information for a specified private cloud for a specified user within a user role
```
PS C:\>$Cloud = Get-SCCloud -Name "Cloud01"
PS C:\> $UserRole = Get-SCUserRole -Name "SelfServiceUsers"
PS C:\> Get-SCCloudUsage -Cloud $Cloud -UserRole $UserRole -UserName "Contoso\PattiFuller"
```

The first command gets the private cloud object named Cloud01 and stores the object in the $Cloud variable.

The second command gets the user role object named SelfServiceUsers and stores the object in the $UserRole variable.

The last command gets the cloud usage information for the private cloud stored in $Cloud and the user named PattiFuller who is in the user role named SelfServiceUsers.
Then, the command displays the cloud usage information to the user.

## PARAMETERS

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
To obtain a user role, use the Get-SCUserRole cmdlet.
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

### -ReturnPerUserRole
Specifies a return per user role.

```yaml
Type: SwitchParameter
Parameter Sets: CloudUsage
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserName
Specifies a the name of a user.
Enter a user name with the format Domain\User.

```yaml
Type: String
Parameter Sets: UserRoleUsageOfCloud
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.

```yaml
Type: UserRole
Parameter Sets: UserRoleUsageOfCloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

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

[Get-SCCloud](xref:VirtualMachineManager/v1/Get-SCCloud.md)

[Get-SCUserRole](xref:VirtualMachineManager/v1/Get-SCUserRole.md)

