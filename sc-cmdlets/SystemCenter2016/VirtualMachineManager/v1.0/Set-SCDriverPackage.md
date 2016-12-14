---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCDriverPackage.md
schema: 2.0.0
ms.assetid: 22728A5D-C537-4719-AF76-847E7E9150C9
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCDriverPackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCDriverPackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCDriverPackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCDriverPackage

## SYNOPSIS
Updates the properties of an existing driver package object.

## SYNTAX

```
Set-SCDriverPackage [-VMMServer <ServerConnection>] [-DriverPackage] <DriverPackage>
 -Tag <System.Collections.Generic.List`1[System.String]> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCDriverPackage** cmdlet updates the properties of an existing driver package object.

## EXAMPLES

### Example 1: Update the tags for a set of driver packages
```
PS C:\>$Drivers = Get-SCDriverPackage -Tag "Production"
PS C:\> ForEach ($Driver in $Drivers) {Set-SCDriverPackage -DriverPackage $Driver -Tag {Production, NewTag}}
```

The first command gets all driver package objects that have a tag value of Production and stores the objects in the $Drivers object array.

The second command uses the **ForEach** statement to add the value "NewTag" to each driver package object stored in $Drivers.

For information about the PowerShell **ForEach** statement, type `Get-Help about_Foreach`.

## PARAMETERS

### -DriverPackage
Specifies a driver package object.

```yaml
Type: DriverPackage
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
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

### DriverPackage[]
This cmdlet returns an array of **DriverPackage** objects.

## NOTES

## RELATED LINKS

[Get-SCDriverPackage](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCDriverPackage.md)

[Remove-SCDriverPackage](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCDriverPackage.md)

