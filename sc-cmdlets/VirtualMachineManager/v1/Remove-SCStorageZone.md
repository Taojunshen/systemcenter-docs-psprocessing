---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageZone.md
schema: 2.0.0
ms.assetid: 2A6EAEB3-06DE-4DCC-B33B-BD2A9FF570B2
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageZone.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageZone.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCStorageZone.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCStorageZone

## SYNOPSIS
Removes a zone from a zone set.

## SYNTAX

```
Remove-SCStorageZone [-StorageZone] <StorageZone> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCStorageZone** cmdlet removes a zone from a zone set.

## EXAMPLES

### Example 1: Remove a zone from a zone set
```
PS C:\>$Zone = Get-SCStorageZone -Name "Zone01"
PS C:\> Remove-SCStorageZone -StorageZone $Zone
```

The first command gets the zone object named Zone01, and then stores that object in the $Zone variable.

The second command removes the zone stored in $Zone from the zone set.

## PARAMETERS

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

[Get-SCStorageZone](xref:VirtualMachineManager/v1/Get-SCStorageZone.md)

[New-SCStorageZone](xref:VirtualMachineManager/v1/New-SCStorageZone.md)

[Set-SCStorageZone](xref:VirtualMachineManager/v1/Set-SCStorageZone.md)

