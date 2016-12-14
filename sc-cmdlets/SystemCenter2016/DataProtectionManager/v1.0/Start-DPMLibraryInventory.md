---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: 70F2D12E-7712-4283-8898-BF0A45755D94
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMLibraryInventory.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMLibraryInventory.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Start-DPMLibraryInventory.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMLibraryInventory

## SYNOPSIS
Starts an inventory of tapes in a DPM library.

## SYNTAX

### FastInventory (Default)
```
Start-DPMLibraryInventory [-DPMLibrary] <Library> [-FastInventory]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DetailedInventory
```
Start-DPMLibraryInventory [-DPMLibrary] <Library> [-DetailedInventory] [-Tape <Media[]>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMLibraryInventory** cmdlet starts an inventory of the tapes in a System Center 2016 - Data Protection Manager (DPM) library.
DPM detects any tape, with or without a bar code, in a library.
You can choose either a detailed inventory or a fast inventory.

For a detailed inventory, DPM reads the header area of the tapes in a library to identify the on-media identifier (OMID) on each tape.

For a fast inventory of a library that has a bar code reader, DPM reads the bar code of each tape in the library.
If a library does not have a bar code reader or a tape does not have a bar code, DPM reads the header area of the tapes to identify the OMID.

## EXAMPLES

### Example 1: Perform a fast inventory
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Start-DPMLibraryInventory -DPMLibrary $DpmLibrary -FastInventory
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library associated with the server, and then stores that object in the $DpmLibrary variable.

The second command starts an inventory on the library object stored in $DpmLibrary.
The command specifies the *FastInventory* parameter, so the command starts a fast inventory.

### Example 2: Perform a detailed inventory
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Start-DPMLibraryInventory -DPMLibrary $DpmLibrary -DetailedInventory
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library associated with the server, and then stores that object in the $DpmLibrary variable.

The second command starts an inventory on the library object stored in $DpmLibrary.
The command uses the *DetailedInventory* parameter, so the command starts a detailed inventory.

## PARAMETERS

### -DetailedInventory
Indicates that DPM performs a detailed inventory on the specified library.

```yaml
Type: SwitchParameter
Parameter Sets: DetailedInventory
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMLibrary
Specifies a DPM library object for which this cmdlet start an inventory.
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

### -FastInventory
Indicates that DPM performs a fast inventory on the specified library.

```yaml
Type: SwitchParameter
Parameter Sets: FastInventory
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter to build a graphical user interface based on cmdlets.
Do not use this parameter in the DPM Management Shell.

```yaml
Type: JobStateChangedEventHandler
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tape
Specifies an array of tape on which this cmdlet operates.
To obtain a **Tape** object, use the Get-DPMTape cmdlet.

```yaml
Type: Media[]
Parameter Sets: DetailedInventory
Aliases: 

Required: False
Position: Named
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

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMLibrary.md)

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMTape.md)

