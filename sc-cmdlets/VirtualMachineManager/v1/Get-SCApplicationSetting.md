---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCApplication.md
schema: 2.0.0
ms.assetid: 8227EAFD-6901-4E0E-8F97-5EA3D99A1624
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCApplicationSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCApplicationSetting

## SYNOPSIS
Gets application settings for an application or application deployment.

## SYNTAX

### ApplicationDeployment (Default)
```
Get-SCApplicationSetting [-VMMServer <ServerConnection>] -ApplicationDeployment <ApplicationDeployment>
 [-Name <String>] [<CommonParameters>]
```

### Application
```
Get-SCApplicationSetting [-VMMServer <ServerConnection>] -Application <SCApplication> [-Name <String>]
 [<CommonParameters>]
```

### ApplicationPackage
```
Get-SCApplicationSetting [-VMMServer <ServerConnection>] -ApplicationPackage <ApplicationPackage>
 [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCApplicationSetting** cmdlet gets application settings for an application or application deployment.

## EXAMPLES

### Example 1: Get all application settings for an application deployment
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SvcWebDeployment01"
PS C:\> $AppSetting = Get-SCApplicationSetting -ApplicationDeployment $AppDeployment
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the application deployment object named SvcWebDeployment01 for the application profile stored in $AppProfile and stores the object in the $AppDeployment variable.

The last command gets the application setting objects for the application deployment stored in $AppDeployment and stores the objects in the $AppSetting array (this example assumes that there are multiple settings for the application).

### Example 2: Get all application settings for an application installed on a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine "VM01"
PS C:\> $Apps = Get-SCApplication -VM $VM
PS C:\> $AppSetting = Get-SCApplicationSetting -ApplicationDeployment $Apps[0]
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the application objects installed on VM01 and stores the objects in the $Apps variable.

The last command gets the application settings for the first application stored in $Apps.

## PARAMETERS

### -Application
Specifies an application object.

```yaml
Type: SCApplication
Parameter Sets: Application
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationDeployment
Specifies an application deployment object.

```yaml
Type: ApplicationDeployment
Parameter Sets: ApplicationDeployment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationPackage
Specifies an application package object.

```yaml
Type: ApplicationPackage
Parameter Sets: ApplicationPackage
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### ApplicationSetting
This cmdlet returns an **ApplicationSetting** object.

## NOTES

## RELATED LINKS

[Get-SCApplication](xref:VirtualMachineManager/v1/Get-SCApplication.md)

[Get-SCApplicationDeployment](xref:VirtualMachineManager/v1/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:VirtualMachineManager/v1/Get-SCApplicationProfile.md)

[Set-SCApplicationSetting](xref:VirtualMachineManager/v1/Set-SCApplicationSetting.md)

