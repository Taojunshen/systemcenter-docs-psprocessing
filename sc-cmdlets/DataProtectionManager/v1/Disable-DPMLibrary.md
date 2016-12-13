---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Enable-DPMLibrary.md
schema: 2.0.0
ms.assetid: E7CCF0E6-9E78-4A3E-9B2D-BEBE1C3A4349
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Disable-DPMLibrary.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Disable-DPMLibrary.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Disable-DPMLibrary.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-DPMLibrary

## SYNOPSIS
Disables DPM libraries.

## SYNTAX

```
Disable-DPMLibrary [-DPMLibrary] <Library[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-DPMLibrary** cmdlet disables one or more System Center 2016 - Data Protection Manager (DPM) libraries.
You can use this cmdlet to disable a tape library in order to perform maintenance or repairs, and then use the Enable-DPMLibrary cmdlet to enable it for use.

## EXAMPLES

### Example 1: Disable libraries for a named server
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Disable-DPMLibrary -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to get the tape libraries for the specified server, and then stores those objects in the $DpmLibrary variable.

The second command disables the libraries stored in $DpmLibrary.

## PARAMETERS

### -DPMLibrary
Specifies an array of DPM library objects.
To obtain a DPM library object, use the Get-DPMLibrary cmdlet.

```yaml
Type: Library[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### Library

## NOTES

## RELATED LINKS

[Enable-DPMLibrary](xref:DataProtectionManager/v1/Enable-DPMLibrary.md)

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

[Rename-DPMLibrary](xref:DataProtectionManager/v1/Rename-DPMLibrary.md)

