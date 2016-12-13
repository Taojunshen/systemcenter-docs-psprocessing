---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: F243BC5A-6C82-4926-AD6C-A616F118897A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeRecatalog.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeRecatalog.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeRecatalog.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMTapeRecatalog

## SYNOPSIS
Recatalogs the data on a tape.

## SYNTAX

```
Start-DPMTapeRecatalog [-Tape] <Media[]> [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMTapeRecatalog** cmdlet recatalogs the data on a tape.
System Center 2016 - Data Protection Manager (DPM) performs this operation before it starts data recovery data from an imported tape.

A recatalog operation determines the recovery points for data on the tape.

## EXAMPLES

### Example 1: Recatalog data on a tape
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTape = Get-DPMTape -DPMLibrary $DpmLibrary
PS C:\> Start-DPMTapeRecatalog -Tape $DpmTape[2]
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the server named Contoso-DPMServer.
The command stores it in the $DpmLibrary variable.

The second command uses the **Get-DPMTape** cmdlet to get the tapes in the library, and then stores the result in the $DpmTape variable.

The third command recatalogs the data.

## PARAMETERS

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

### Job

## NOTES

## RELATED LINKS

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

[Get-DPMTape](xref:DataProtectionManager/v1/Get-DPMTape.md)

