---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryShare.md
schema: 2.0.0
ms.assetid: 94B234A5-F844-4E70-B6AC-2A8CFE766567
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLibraryShare

## SYNOPSIS
Changes the description property of a VMM library share object.

## SYNTAX

```
Set-SCLibraryShare [-LibraryShare] <LibraryShare> [-Description <String>] [-AddDefaultResources]
 [-UseAlternateDataStream <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLibraryShare** cmdlet changes the description property of a Virtual Machine Manager (VMM) library share object.

## EXAMPLES

### Example 1: Change the description of a library share
```
PS C:\>$LibShare = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "FileShare01" } 
PS C:\> Set-SCLibraryShare -LibraryShare $LibShare -Description "Library share for Test"
```

The first command retrieves the library share object named FileShare01 on LibraryServer01 from the VMM library on VMMServer01 and then stores the library share object in the $LibShare variable.

The second command changes the description for FileShare01 to "Library share for Test".

## PARAMETERS

### -AddDefaultResources
Indicates that the default resources for a library share are added.

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

### -Description
Specifies a description for the library share.

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

### -LibraryShare
Specifies a VMM library share object.

```yaml
Type: LibraryShare
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -UseAlternateDataStream
Indicates whether to use AlternateDataStream.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LibraryShare
This cmdlet returns a **LibraryShare** object.

## NOTES

## RELATED LINKS

[Add-SCLibraryShare](xref:VirtualMachineManager/v1/Add-SCLibraryShare.md)

[Find-SCLibraryShare](xref:VirtualMachineManager/v1/Find-SCLibraryShare.md)

[Get-SCLibraryShare](xref:VirtualMachineManager/v1/Get-SCLibraryShare.md)

[Read-SCLibraryShare](xref:VirtualMachineManager/v1/Read-SCLibraryShare.md)

[Remove-SCLibraryShare](xref:VirtualMachineManager/v1/Remove-SCLibraryShare.md)

