---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9A01EA23-0FF7-4BC8-B9F2-4109784F1B2F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMLibrary.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMLibrary.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMLibrary.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Enable-DPMLibrary

## SYNOPSIS
Enables DPM libraries.

## SYNTAX

```
Enable-DPMLibrary [-DPMLibrary] <Library[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DPMLibrary** cmdlet enables one or more System Center 2016 - Data Protection Manager (DPM) libraries.
You can use the [Disable-DPMLibrary](./Disable-DPMLibrary.md) cmdlet to disable a tape library in order to perform maintenance or repairs, and then use this cmdlet to enable it for use.

## EXAMPLES

### Example 1: Enable libraries for a named server
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Enable-DPMLibrary -DPMLibrary $DpmLibrary
```

The first command uses the [Get-DPMLibrary](./Get-DPMLibrary.md) cmdlet to get the tape libraries for the specified server, and then stores those objects in the $DpmLibrary variable.

The second command enables the libraries stored in $DpmLibrary.

## PARAMETERS

### -DPMLibrary
Specifies an array of DPM library objects that this cmdlet enables.
To obtain a DPM library object, use the **Get-DPMLibrary** cmdlet.

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

[Disable-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMLibrary.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Rename-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMLibrary.md)
