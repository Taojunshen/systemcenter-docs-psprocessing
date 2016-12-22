---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 8D9923C5-8694-42E7-9500-67C20CD28BC5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCapabilityProfile

## SYNOPSIS
Gets a capability profile.

## SYNTAX

### FromName
```
Get-SCCapabilityProfile [-Name <String>] [-VMMServer <ServerConnection>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### FromId
```
Get-SCCapabilityProfile -ID <Guid> [-VMMServer <ServerConnection>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCapabilityProfile** cmdlet gets one or more capability profile objects in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Get a capability profile by its name
```
PS C:\> Get-SCCapabilityProfile -Name "CapabilityProf01"
```

This command gets the capability profile object named CapabilityProf01 and displays information about the object to the user.

### Example 2: Get a capability profile by using the on behalf of parameters
```
PS C:\> $UR = Get-SCUserRole -Name "UR01"
PS C:\> Get-SCCapabilityProfile -Name "CapabilityProf01" -OnBehalfOfUserRole $UR -OnBehalfOfUser "user01@contoso.com"
```

The first command gets the user role object named UR01 and stores the object in the $UR variable.

The second command gets the capability profile object named CapabilityProf01 filtered by the user role stored in $UR and by the on behalf of user named user01@contoso.com.
The cmdlet then displays information about the object to the user.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: FromId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: FromName
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

### CloudCapabilityProfile
This cmdlet returns a **CloudCapabilityProfile** object.

## NOTES

## RELATED LINKS

[New-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md)

[Remove-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCapabilityProfile.md)

[Set-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md)

[Test-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md)

