---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMChildDatasource.md
schema: 2.0.0
ms.assetid: 9D5FB7D7-361B-4D09-A80F-CF6B67DFF80A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMChildDatasource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMChildDatasource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMChildDatasource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMChildDatasource

## SYNOPSIS
Returns the protectable file system objects in a data source.

## SYNTAX

```
Get-DPMChildDatasource [-ChildDatasource] <ProtectableObject> [-Inquire] [-Async]
 [[-ProtectionGroup] <ProtectionGroup>] [-Tag <Object>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMChildDatasource** cmdlet returns the protectable file system objects, such as folders, that are in a data source, such as a file system volume.
You can protect file systems at the child data source level, but you can protect applications only at the data source level.

## EXAMPLES

### Example 1: Get a child data source
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Get-DPMChildDatasource -ChildDatasource $PObjects[1] -Inquire
```

The first command gets all protection groups from the DPM server named DPMServer07, and then stores these groups in the $PGroup variable.
You cannot edit these protection groups.

The second command gets the data source for the list of protection groups in $PGroup, and then stores this data source in the $PObjects variable.

The final command gets a list of the child data sources from element 1 of the $PObjects array variable.
The command uses the *Inquire* parameter.
Therefore, the command queries the protected computer.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

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

### -ChildDatasource
Specifies a data source, such as a folder in a file system, that System Center 2016 - Data Protection Manager (DPM) can protect individually.

```yaml
Type: ProtectableObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Inquire
Indicates that the cmdlet queries the protected computer and returns the data sources or child data sources on it.

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

### -ProtectionGroup
Specifies a protection group for which this cmdlet gets a data source.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Specifies a custom property that distinguishes the replies to each asynchronous call.
You can use parameter if you build a graphical user interface by using cmdlets.
Do not use this parameter if you work with the DPM Management Shell.

```yaml
Type: Object
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

### ChildDatasource

## NOTES

## RELATED LINKS

[Add-DPMChildDatasource](xref:DataProtectionManager/v1/Add-DPMChildDatasource.md)

[Get-DPMDatasource](xref:DataProtectionManager/v1/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Remove-DPMChildDatasource](xref:DataProtectionManager/v1/Remove-DPMChildDatasource.md)

