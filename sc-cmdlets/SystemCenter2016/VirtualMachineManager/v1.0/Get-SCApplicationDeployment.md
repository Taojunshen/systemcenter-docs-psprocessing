---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCApplicationDeployment.md
schema: 2.0.0
ms.assetid: A5FEDCB7-C2A0-49B9-970D-3BB311316091
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCApplicationDeployment

## SYNOPSIS
Gets the applications that have been added to an application profile.

## SYNTAX

### AP (Default)
```
Get-SCApplicationDeployment [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 [-Name <String>] [<CommonParameters>]
```

### ID
```
Get-SCApplicationDeployment [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicationDeployment** cmdlet gets the applications that have been added to an application profile.

## EXAMPLES

### Example 1: Get all application deployments associated with a specific application profile
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile
PS C:\> $AppDeployment
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets all of the application deployment objects for the application profile stored in $AppProfile and stores the objects in the $AppDeployment array.

The last command displays the application deployment objects stored in $AppDeployment to the user.

## PARAMETERS

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: AP
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: AP
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

### ApplicationDeployment
This cmdlet returns an **ApplicationDeployment** object.

## NOTES

## RELATED LINKS

[Add-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationProfile.md)

[Remove-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCApplicationDeployment.md)

[Set-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationDeployment.md)

