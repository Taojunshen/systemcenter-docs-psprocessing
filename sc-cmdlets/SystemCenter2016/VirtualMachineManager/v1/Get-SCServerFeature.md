---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCServerFeature.md
schema: 2.0.0
ms.assetid: 24074D71-483E-4270-8AE9-78CCF6050D17
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCServerFeature.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCServerFeature.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCServerFeature.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCServerFeature

## SYNOPSIS
Gets the operating system roles and features that have been added to a guest operating system profile.

## SYNTAX

### AllParamSet (Default)
```
Get-SCServerFeature [-VMMServer <ServerConnection>] [-Name <String>] [<CommonParameters>]
```

### IDParamSet
```
Get-SCServerFeature [-VMMServer <ServerConnection>] -ID <Guid> [-Name <String>] [<CommonParameters>]
```

### OSProfileParamSet
```
Get-SCServerFeature [-VMMServer <ServerConnection>] -GuestOSProfile <GuestOSProfile> [-Name <String>]
 [<CommonParameters>]
```

### TemplateParamSet
```
Get-SCServerFeature [-VMMServer <ServerConnection>] -VMTemplate <Template> [-Name <String>]
 [<CommonParameters>]
```

### OSParamSet
```
Get-SCServerFeature [-VMMServer <ServerConnection>] -OperatingSystem <OperatingSystem> [-Name <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCServerFeature** cmdlet gets the operating system roles and features that have been added to a guest operating system profile.

## EXAMPLES

### Example 1: Get all operating system features than have been added to a guest operating system profile
```
PS C:\>$OSProfile = Get-SCGuestOSProfile -Name "NewOSProfile01"
PS C:\> $ServerFeature = Get-SCServerFeature -GuestOSProfile $OSProfile
```

The first command gets the guest operating system profile object named NewOSProfile01 and stores the object in the $OSProfile variable.

The second command gets all of the server feature objects that have been added to the guest operating system profile stored in $OSProfile and stores the objects in the $ServerFeature array.

## PARAMETERS

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
Parameter Sets: OSProfileParamSet
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
Parameter Sets: IDParamSet
Aliases: 

Required: True
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

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To list the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: OSParamSet
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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: TemplateParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ServerFeature
This cmdlet returns a **ServerFeature** object.

## NOTES

## RELATED LINKS

[Add-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCServerFeature.md)

[Get-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCGuestOSProfile.md)

[Remove-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCServerFeature.md)

