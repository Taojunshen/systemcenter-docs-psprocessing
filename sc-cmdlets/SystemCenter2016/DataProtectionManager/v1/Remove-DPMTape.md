---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Add-DPMTape.md
schema: 2.0.0
ms.assetid: 30BC7446-79F1-4350-B09F-13C0156B6E8B
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMTape.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMTape.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Remove-DPMTape.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-DPMTape

## SYNOPSIS
Removes a tape from a DPM library.

## SYNTAX

```
Remove-DPMTape [-DPMLibrary] <Library> [-Tape] <Media[]> [-Async]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DPMTape** cmdlet removes a tape from a System Center 2016 - Data Protection Manager (DPM) library.

## EXAMPLES

### Example 1: Remove a tape from a library
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTape = Get-DPMTape -DPMLibrary $DpmLibrary
PS C:\> Unlock-DPMLibraryDoor -DPMLibrary $DpmLibrary
PS C:\> Remove-DPMTape -DPMLibrary $DpmLibrary -Tape $DpmTape[2]
```

The first command uses the **Get-DPMLibrary** cmdlet to retrieve the library for the server.
The command stores the result in the $DpmLibrary variable.

The second command uses the **Get-DPMTape** cmdlet to retrieve the tape object.
The command stores the result in the $DpmTape variable.

The third command uses the **Unlock-DPMLibraryDoor** cmdlet to unlock the tape door.

The final command removes the third tape from the library.

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
Specifies a DPM library from which this cmdlet removes a tape.
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

### -Tape
Specifies an array of tape objects that this cmdlet removes.
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

```yaml
Type: Media[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

[Add-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Add-DPMTape.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMLibrary.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMTape.md)

[Set-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1/Set-DPMTape.md)

[Unlock-DPMLibraryDoor](xref:SystemCenter2016/DataProtectionManager/v1/Unlock-DPMLibraryDoor.md)

