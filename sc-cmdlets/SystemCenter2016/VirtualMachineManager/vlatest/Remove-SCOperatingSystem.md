---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CA99FFE7-2870-4DF4-87DA-741E3FDE819F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOperatingSystem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOperatingSystem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOperatingSystem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOperatingSystem

## SYNOPSIS
Deletes an operating system from an application profile.

## SYNTAX

```
Remove-SCOperatingSystem [-VMMServer <ServerConnection>] -ApplicationProfile <ApplicationProfile>
 -OperatingSystem <OperatingSystem> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOperatingSystem** cmdlet deletes an operating system from an application profile.

## EXAMPLES

### Example 1: Remove all operating systems from a specified application profile
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $OS = $AppProfile.OperatingSystems[0]
PS C:\> Remove-SCOperatingSystem -ApplicationProfile $AppProfile -OperatingSystem $OS
```

The first command gets the application profile object named SvcWebAppProfile01 and stores it in the $AppProfile variable.

The second command gets the first operating system object stored in the OperatingSystems property of the application profile stored in $AppProfile and stores the object in the $OS variable.

The last command removes the operating system stored in $OS from the application profile stored in $AppProfile.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCOperatingSystem.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md)

