---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCApplicationProfile.md
schema: 2.0.0
ms.assetid: 331DC1D4-FE26-429F-93C5-C5FB50A4FDC5
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCApplicationProfile

## SYNOPSIS
Gets application profiles.

## SYNTAX

### All (Default)
```
Get-SCApplicationProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### GetByName
```
Get-SCApplicationProfile [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### GetByVMTemplate
```
Get-SCApplicationProfile [-VMMServer <ServerConnection>] -VMTemplate <Template> [<CommonParameters>]
```

### GetByApplicationHostTemplate
```
Get-SCApplicationProfile [-VMMServer <ServerConnection>] -ApplicationHostTemplate <ApplicationHostTemplate>
 [<CommonParameters>]
```

### ID
```
Get-SCApplicationProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicationProfile** cmdlet gets application profiles.
You can get individual profiles by using parameters such as *Name* or *ID*, or get all application profiles in Virtual Machine Manager (VMM) by using the *All* parameter.

## EXAMPLES

### Example 1: Get an application profile by its name
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppProfile
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command displays information about the application profile stored in $AppProfile to the user.

### Example 2: Get all application profiles
```
PS C:\>$AppProfiles = Get-SCApplicationProfile -All
PS C:\> $AppProfiles[0]
```

The first command gets all application profile objects and stores them in the $AppProfiles array.

The second command displays information about only the first object in the $AppProfiles array to the user.

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

### -ApplicationHostTemplate
Specifies an application host template object.

```yaml
Type: ApplicationHostTemplate
Parameter Sets: GetByApplicationHostTemplate
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

### -Name
Specifies the name of a VMM object.

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
Parameter Sets: GetByVMTemplate
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

### ApplicationProfile
This cmdlet returns an **ApplicationProfile** object.

## NOTES

## RELATED LINKS

[New-SCApplicationProfile](xref:VirtualMachineManager/v1/New-SCApplicationProfile.md)

[Remove-SCApplicationProfile](xref:VirtualMachineManager/v1/Remove-SCApplicationProfile.md)

[Set-SCApplicationProfile](xref:VirtualMachineManager/v1/Set-SCApplicationProfile.md)

