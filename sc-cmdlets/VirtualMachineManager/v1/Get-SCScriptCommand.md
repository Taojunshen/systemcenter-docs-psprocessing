---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCScriptCommand.md
schema: 2.0.0
ms.assetid: 84296E54-B12F-4059-9591-A1F4A7209A24
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCScriptCommand

## SYNOPSIS
Gets all script commands for an application profile, application deployment, or host profile.

## SYNTAX

### ApplicationProfile
```
Get-SCScriptCommand -ApplicationProfile <ApplicationProfile> [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### ApplicationDeployment
```
Get-SCScriptCommand -ApplicationDeployment <ApplicationDeployment> [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

### PhysicalComputerProfile
```
Get-SCScriptCommand -PhysicalComputerProfile <PhysicalComputerProfile> [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCScriptCommand** cmdlet gets all script commands for an application profile, application deployment, or host profile.

## EXAMPLES

### Example 1: Get all script commands associated with an application profile
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ScriptCommand = Get-SCScriptCommand -ApplicationProfile $AppProfile
PS C:\> $ScriptCommand
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets all script commands for the application profile object stored in $AppProfile and stores the objects in the $ScriptCommand array.

The last command displays information about all of the script command objects stored in the $ScriptCommand array to the user.

### Example 2: Get all of the script commands associated with an application deployment
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile
PS C:\> $ScriptCommand = Get-SCScriptCommand -ApplicationDeployment $AppDeployment
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the application deployment object for the application profile stored in $AppProfile and stores the object in the $AppDeployment variable.

The last command gets all of the script commands associated with the application deployment object stored in $AppDeployment and stores the script commands in $ScriptCommand.

## PARAMETERS

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

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: ApplicationProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: PhysicalComputerProfile
Aliases: VMHostProfile

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

### ScriptCommand
This cmdlet returns a **ScriptCommand** object.

## NOTES

## RELATED LINKS

[Add-SCScriptCommand](xref:VirtualMachineManager/v1/Add-SCScriptCommand.md)

[Invoke-SCScriptCommand](xref:VirtualMachineManager/v1/Invoke-SCScriptCommand.md)

[Remove-SCScriptCommand](xref:VirtualMachineManager/v1/Remove-SCScriptCommand.md)

[Set-SCScriptCommand](xref:VirtualMachineManager/v1/Set-SCScriptCommand.md)
