---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCComputerTierConfiguration.md
schema: 2.0.0
ms.assetid: 38BDCB63-A1D0-4C78-8114-FB94D087A28A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMConfiguration

## SYNOPSIS
Gets the virtual machine configuration information for a service configuration or computer tier configuration.

## SYNTAX

### TierConfig
```
Get-SCVMConfiguration [-VMMServer <ServerConnection>]
 -ComputerTierConfiguration <BaseComputerTierConfiguration> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ServiceConfig
```
Get-SCVMConfiguration [-VMMServer <ServerConnection>] -ServiceConfiguration <ServiceConfiguration>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### All
```
Get-SCVMConfiguration [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVMConfiguration [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMConfiguration** cmdlet gets virtual machine configuration information for a service configuration or computer tier configuration.

## EXAMPLES

### Example 1: Get all configuration information for a virtual machine within a computer tier configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01" 
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfig = Get-SCVMConfiguration -ComputerTierConfiguration $TierConfig
PS C:\> $VMConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command gets the virtual machine configuration for the computer tier configuration stored in $TierConfig and stores the object in the $VMConfig variable.

The last command displays the properties of the virtual machine configuration stored in $VMConfig to the user.

### Example 2: Get all configuration information for a virtual machine within a service configuration
```
PS C:\>$ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $VMConfigs = Get-SCVMConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $VMConfigs
```

The first command gets the service configuration named Service01 and stores the object in the $ServiceConfig variable.

The second command gets all virtrual machine configurations for the service configuration stored in $ServiceConfig and stores the objects in the $VMConfigs variable.

The last command displays the properties of the virtual machine configurations stored in $VMConfigs to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerTierConfiguration
Specifies a computer tier configuration object.

```yaml
Type: BaseComputerTierConfiguration
Parameter Sets: TierConfig
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the Get-SCUserRole cmdlet.

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

### -ServiceConfiguration
Specifies a service configuration object.

```yaml
Type: ServiceConfiguration
Parameter Sets: ServiceConfig
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### VMConfiguration
This cmdlet returns a **VMConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:VirtualMachineManager/v1/Get-SCComputerTierConfiguration.md)

[Get-SCServiceConfiguration](xref:VirtualMachineManager/v1/Get-SCServiceConfiguration.md)

[New-SCVMConfiguration](xref:VirtualMachineManager/v1/New-SCVMConfiguration.md)

[Remove-SCVMConfiguration](xref:VirtualMachineManager/v1/Remove-SCVMConfiguration.md)

[Set-SCVMConfiguration](xref:VirtualMachineManager/v1/Set-SCVMConfiguration.md)

[Update-SCVMConfiguration](xref:VirtualMachineManager/v1/Update-SCVMConfiguration.md)

