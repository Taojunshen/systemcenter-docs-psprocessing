---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 531048DF-F761-4F38-9768-5D0B124E5CC8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMTape.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMTape.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMTape.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMTape

## SYNOPSIS
Marks a tape as Archive, Cleaner, Free or Not Free.

## SYNTAX

### Archive
```
Set-DPMTape [-Tape] <Media[]> [-Archive] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Cleaner
```
Set-DPMTape [-Tape] <Media[]> [-Cleaner] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Free
```
Set-DPMTape [-Tape] <Media[]> [-Free] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Unfree
```
Set-DPMTape [-Tape] <Media[]> [-NotFree] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMTape** cmdlet marks a tape as Archive, Cleaner, Free, or Not Free.

## EXAMPLES

### Example 1: Mark a tape as free
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTape = Get-Tape -DPMLibrary $DpmLibrary
PS C:\> Set-DPMTape -Tape $DpmTape[1] -Free
```

The first command uses the **Get-DPMLibrary** cmdlet to retrieve the library for the server, and then stores it in the $DpmLibrary variable.

The second command uses the **Get-DPMTape** cmdlet to retrieve the tape object, and then stores it in the $DpmTape variable.

The third command sets the second tape as Free.

## PARAMETERS

### -Archive
Indicates that the media is an archive tape.

```yaml
Type: SwitchParameter
Parameter Sets: Archive
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cleaner
Indicates that the media is a cleaning tape.

```yaml
Type: SwitchParameter
Parameter Sets: Cleaner
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Free
Indicates that the media is free for use.

```yaml
Type: SwitchParameter
Parameter Sets: Free
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotFree
Indicates that the media is not free for use.

```yaml
Type: SwitchParameter
Parameter Sets: Unfree
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -Tape
Specifies an array of tapes on which this cmdlet operates.
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

```yaml
Type: Media[]
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

### Tape

## NOTES

## RELATED LINKS

[Add-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Add-DPMTape.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md)

[Remove-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Remove-DPMTape.md)

