---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9B147A56-D14D-49A4-90F7-B0D372D58844
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZone.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZone.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageZone.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageZone

## SYNOPSIS
Modifies an existing zone in a zone set.

## SYNTAX

```
Set-SCStorageZone [-StorageZone] <StorageZone> [-Name <String>] [-Description <String>]
 [-AddZoneAlias <StorageZoneAlias[]>] [-RemoveZoneAlias <StorageZoneAlias[]>] [-AddZoneMembership <String[]>]
 [-RemoveZoneMembership <String[]>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageZone** cmdlet modifies an existing zone in a zone set.

## EXAMPLES

### Example 1: Modify an existing zone
```
PS C:\> $Zone = Get-SCStorageZone -Name "Zone01"
PS C:\> $Alias = Get-SCStorageZoneAlias -Name "MyArrayPorts"
PS C:\> $Members = @()
PS C:\> $Members += "D113ED3B8A310220"
PS C:\> $Members += "C003FF3B8A610000"
PS C:\> Set-SCStorageZone -StorageZone $Zone -Description "Update zone for vm host" -AddZoneMembership $Members -RemoveZoneAlias $Alias
```

The first command gets the zone object named Zone01, and stores that object in the $Zone variable.

The second command gets the storage zone alias named MyArrayPorts, and stores the object in the $Alias variable.

The third command creates an array named $Members.
The fourth and fifth commands populate the $Members array.

The last command adds a description and members to the zone stored in $Zone.
The command removes the specified aliases.

## PARAMETERS

### -AddZoneAlias
Specifies an array of zone aliases that represents one or more world-wide port names.
To obtain a **StorageZoneAlias** object, use the **Get-SCStorageZoneAlias** cmdlet.

```yaml
Type: StorageZoneAlias[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddZoneMembership
Specifies an array of zone members for this cmdlet to add.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the storage zone.

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

### -JobVariable
Specifies the name of a variable that you use to track and store job progress.

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

### -Name
Specifies the name of the new storage zone.

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

### -RemoveZoneAlias
Specifies an array of storage zone aliases for this cmdlet to remove.

```yaml
Type: StorageZoneAlias[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveZoneMembership
Specifies an array of zone members for this cmdlet to remove.

```yaml
Type: String[]
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

### -StorageZone
Specifies a Fibre Channel zone in a zone set.

```yaml
Type: StorageZone
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageZone
This cmdlet returns a **StorageZone** object.

## NOTES

## RELATED LINKS

[Get-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZone.md)

[Get-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageZoneAlias.md)

[New-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageZone.md)

[Remove-SCStorageZone](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageZone.md)

