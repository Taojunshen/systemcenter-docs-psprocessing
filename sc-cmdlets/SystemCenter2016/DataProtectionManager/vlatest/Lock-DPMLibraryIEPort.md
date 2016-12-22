---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9A932D2D-5CB6-4E2B-A1EA-BAC5AC18DA00
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryIEPort.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryIEPort.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryIEPort.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Lock-DPMLibraryIEPort

## SYNOPSIS
Locks the I/E port for a DPM library and loads the media present in the I/E port.

## SYNTAX

```
Lock-DPMLibraryIEPort [-DPMLibrary] <Library> [-Async]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Lock-DPMLibraryIEPort** cmdlet locks the insert/eject (I/E) port for a System Center 2016 - Data Protection Manager (DPM) library and loads the media present in the I/E port into the slot.

## EXAMPLES

### Example 1: Lock an I/E port
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Lock-DPMLibraryDoor -DPMLibrary $DpmLibrary
```

The first command uses the **Get-DPMLibrary** cmdlet to get the library for the named server, and then stores the library object in the $DpmLibrary variable.

The second command locks the object stored in $DpmLibrary.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DPMLibrary
Specifies a DPM library object for which this cmdlet locks the I/E port.
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

[Unlock-DPMLibraryIEPort](xref:SystemCenter2016/DataProtectionManager/vlatest/Unlock-DPMLibraryIEPort.md)

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

