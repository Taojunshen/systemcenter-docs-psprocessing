---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: 7E90D3A5-0687-48EB-80BD-92DB96B3FE9D
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Add-DPMTape.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Add-DPMTape.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Add-DPMTape.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-DPMTape

## SYNOPSIS
Adds a tape to a DPM library.

## SYNTAX

```
Add-DPMTape [-DPMLibrary] <Library> [-Async] [-JobStateChangedEventHandler <JobStateChangedEventHandler>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DPMTape** cmdlet adds a tape to a System Center 2016 - Data Protection Manager (DPM) library.

## EXAMPLES

### Example 1: Add a tape to a library
```
PS C:\>$DpmMLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> Add-DPMTape -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to retrieve the library for the server, and then stores it in the $DpmLibrary variable.

The second command adds a tape to the library.

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

### -DPMLibrary
Specifies a DPM library object to which this cmdlet adds a tape.
To obtain a DPM library object, use the Get-DPMLibrary cmdlet.

```yaml
Type: Library
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter to build a graphical user interface based on cmdlets.
Do not use this parameter in the DPM Management Shell.

```yaml
Type: JobStateChangedEventHandler
Parameter Sets: (All)
Aliases: Handler

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

## NOTES

## RELATED LINKS

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMLibrary.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMTape.md)

[Remove-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Remove-DPMTape.md)

[Set-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMTape.md)

