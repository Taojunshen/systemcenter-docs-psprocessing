---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCServiceConfiguration.md
schema: 2.0.0
ms.assetid: D8B2FE1B-7BAE-43D3-90D6-7B01B119507C
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCServiceConfiguration

## SYNOPSIS
Gets a service configuration object stored in the VMM library.

## SYNTAX

```
Get-SCServiceConfiguration [-VMMServer <ServerConnection>] [-Name <String>] [-ID <Guid>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCServiceConfiguration** cmdlet gets one or more service configuration objects stored in the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Get all service configuration objects in the library
```
PS C:\>$SvcConfigs = Get-SCServiceConfiguration -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Service" }
PS C:\> $SvcConfigs
```

The first command gets all service configuration objects on VMMServer01, selects from the results the service configuration objects that contain Service in their name, and then stores the objects in the $SvcConfigs variable.

The second command displays the properties of the service configuration objects to the user.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

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

### ServiceConfiguration
This cmdlet returns a **ServiceConfiguration** object.

## NOTES

## RELATED LINKS

[New-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCServiceConfiguration.md)

[Remove-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCServiceConfiguration.md)

[Set-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCServiceConfiguration.md)

[Update-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Update-SCServiceConfiguration.md)

