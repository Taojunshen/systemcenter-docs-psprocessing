---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Disable-DPMTapeDrive.md
schema: 2.0.0
ms.assetid: 22CC3BF7-DCCF-4727-9CD6-D8DFFED06A38
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMTapeDrive.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMTapeDrive.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Enable-DPMTapeDrive.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-DPMTapeDrive

## SYNOPSIS
Enables the tape drives in the DPM library.

## SYNTAX

```
Enable-DPMTapeDrive [-TapeDrive] <Drive[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-DPMTapeDrive** cmdlet enables the tape drives in the System Center 2016 - Data Protection Manager (DPM) library.

To determine if a tape drive is enabled, use the Get-DPMTapeDrive cmdlet.

## EXAMPLES

### Example 1: Enable a tape drive in a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTapeDrive = Get-DPMTapeDrive -DPMLibrary $DpmLibrary
PS C:\> Enable-DPMTapeDrive -TapeDrive $DpmTapeDrive
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the server named Contoso-DPMServer.
The command stores the library in the $DpmLibrary variable.

The second command uses the **Get-DPMTapeDrive** cmdlet to get the tape drives in the library, and then stores them in the variable named $DpmTapeDrive.

The third command enables the tape drive.

## PARAMETERS

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

### -TapeDrive
Specifies an array of tape drives that this cmdlet enables.

```yaml
Type: Drive[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

## NOTES

## RELATED LINKS

[Disable-DPMTapeDrive](xref:SystemCenter2016/DataProtectionManager/vlatest/Disable-DPMTapeDrive.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Get-DPMTapeDrive](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTapeDrive.md)

