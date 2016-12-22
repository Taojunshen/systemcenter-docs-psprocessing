---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 01F6CE5A-DA64-40B5-8CCB-2AA8A7EBD304
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCApplicationHost

## SYNOPSIS
Gets the application host for a service or for all services.

## SYNTAX

### All (Default)
```
Get-SCApplicationHost [-VMMServer <ServerConnection>] [-All] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### GetByService
```
Get-SCApplicationHost [-VMMServer <ServerConnection>] [-Name <String>] -Service <Service>
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### GetByName
```
Get-SCApplicationHost [-VMMServer <ServerConnection>] -Name <String> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCApplicationHost [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicationHost** cmdlet gets the application host for a service or, when used with the *All* parameter, for all services.

## EXAMPLES

### Example 1: Get the application host for a service
```
PS C:\> $Service = Get-SCService -Name "Service01"
PS C:\> $ApplicationHost = Get-SCApplicationHost -Service $Service
PS C:\> $ApplicationHost
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command gets the application host for the service stored in $Service and stores the variable in the $ApplicationHost variable.

The last command displays the properties of the application host stored in $ApplicationHost to the user.

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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: GetByService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: GetByName
Aliases: 

Required: True
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

### -Service
Specifies a VMM service object.

```yaml
Type: Service
Parameter Sets: GetByService
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

### ApplicationHost
This cmdlet returns an **ApplicationHost** object.

## NOTES

## RELATED LINKS

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

