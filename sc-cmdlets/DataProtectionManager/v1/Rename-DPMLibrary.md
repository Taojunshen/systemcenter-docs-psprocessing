---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Disable-DPMLibrary.md
schema: 2.0.0
ms.assetid: C7504FE6-698D-4AE1-8652-0A9F5E69BC83
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Rename-DPMLibrary.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Rename-DPMLibrary.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Rename-DPMLibrary.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Rename-DPMLibrary

## SYNOPSIS
Renames a DPM library.

## SYNTAX

```
Rename-DPMLibrary [-DPMLibrary] <Library> [-NewName] <String> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Rename-DPMLibrary** cmdlet renames a System Center 2016 - Data Protection Manager (DPM) library in the DPM Administrator Console.

## EXAMPLES

### Example 1: Rename a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Rename-DPMLibrary -DPMLibrary $DpmLibrary -NewName "Library Western 03"
```

The first command uses the **Get-DPMLibrary** cmdlet to get the tape library for the specified server, and stores that object in the $DpmLibrary variable.

The second command changes the name the library stored in the $DpmLibrary variable to Library Western 03.

## PARAMETERS

### -DPMLibrary
Specifies a DPM library object that this cmdlet renames.
To obtain a DPM library object, use the Get-DPMLibrary cmdlet.

```yaml
Type: Library
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the library.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Accept pipeline input: True (ByPropertyName)
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

[Disable-DPMLibrary](xref:DataProtectionManager/v1/Disable-DPMLibrary.md)

[Enable-DPMLibrary](xref:DataProtectionManager/v1/Enable-DPMLibrary.md)

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

