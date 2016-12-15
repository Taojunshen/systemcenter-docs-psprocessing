---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCApplicationProfile.md
schema: 2.0.0
ms.assetid: D0E31033-481E-4259-BE7E-1A354E9D9E06
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCOperatingSystem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCOperatingSystem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCOperatingSystem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCOperatingSystem

## SYNOPSIS
Adds an operating system to an application profile to specify which operating systems the application profile is compatible with.

## SYNTAX

```
Add-SCOperatingSystem [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 -OperatingSystem <OperatingSystem> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOperatingSystem** cmdlet adds an operating system to an application profile object.
Setting the operating system for an application profile determines which operating systems the profile is compatibile with.
If no operating system is set, by default the profile is compatible with all operating systems.

## EXAMPLES

### Example 1: Add an operating system to an application profile
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Enterprise"}
PS C:\> Add-SCOperatingSystem -ApplicationProfile $AppProfile -OperatingSystem $OS
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the operating system object named 64-bit edition of Windows Server 2008 R2 Enterprise from VMMServer01 and stores the object in the $OS variable.

The last command adds the operating system stores in $OS to the application profile stored in $AppProfile.

## PARAMETERS

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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
To list the names of all available operating systems in Virtual Machine Manager (VMM), type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
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

### OperatingSystem
This cmdlet returns an **OperatingSystem** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md)

[Remove-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOperatingSystem.md)

