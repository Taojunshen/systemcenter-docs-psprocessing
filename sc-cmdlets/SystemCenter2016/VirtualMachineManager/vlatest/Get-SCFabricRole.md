---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CA67424D-FBD0-4DE6-9554-641722E2A705
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCFabricRole

## SYNOPSIS
Gets a fabric role.

## SYNTAX

### ByNetworkService (Default)
```
Get-SCFabricRole [-VMMServer <ServerConnection>] -NetworkService <NetworkService> [-Name <String>]
 [-Type <FabricRoleType>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ByID
```
Get-SCFabricRole [-VMMServer <ServerConnection>] -ID <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCFabricRole** cmdlet gets a fabric role.

## EXAMPLES

### Example 1: Gets the existing fabric roles
```
PS C:\> $NetworkService = Get-SCNetworkService -Name "ns"
PS C:\> $FabricRole = Get-SCFabricRole -NetworkService $NetworkService -Name "fr"
```

The first command gets a network service by using the **Get-SCNetworkService** cmdlet, and then stores it in the $NetworkService variable.

The second command gets the existing fabric roles for the service in $NetworkService that have the specified name.

## PARAMETERS

### -ID
Specifies the ID of the fabric role to get.

```yaml
Type: Guid
Parameter Sets: ByID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the fabric role to get.

```yaml
Type: String
Parameter Sets: ByNetworkService
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkService
Specifies a network service object.

```yaml
Type: NetworkService
Parameter Sets: ByNetworkService
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

### -Type
Specifies the type.
Valid values are: 

- Unknown
- Gateway
- LoadBalancer

```yaml
Type: FabricRoleType
Parameter Sets: ByNetworkService
Aliases: 
Accepted values: Unknown, Gateway, LoadBalancer

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkService.md)

