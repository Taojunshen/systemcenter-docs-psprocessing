---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EB36CF35-3A3A-4EA6-8FB0-077AE9399A94
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryDoor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryDoor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Lock-DPMLibraryDoor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Lock-DPMLibraryDoor

## SYNOPSIS
Locks the door of a DPM library.

## SYNTAX

```
Lock-DPMLibraryDoor [-DPMLibrary] <Library> [-Async]
 [-DoorAccessJobStateChangeEventHandler <DoorAccessJobStateChangeEventHandler>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Lock-DPMLibraryDoor** cmdlet locks the door of a System Center 2016 - Data Protection Manager (DPM) library.

## EXAMPLES

### Example 1: Lock a library door
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "DPMServer07"
PS C:\> Lock-DPMLibraryDoor -DPMLibrary $DpmLibrary[0]
```

The first command gets the libraries associated with the server, and then stores the library objects in the $DpmLibrary variable.

The second command locks the library door for the first library object stored in $DpmLibrary.
This DPM server has more than one library.
Therefore, the command uses standard Windows PowerShell array syntax to specify the first member of the $DpmLibrary array.

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

### -DoorAccessJobStateChangeEventHandler
Specifies an event handler for certain door access events.
You can use this parameter to update a GUI that runs in Windows PowerShell, but do not use it in the Windows PowerShell console.

```yaml
Type: DoorAccessJobStateChangeEventHandler
Parameter Sets: (All)
Aliases: Handler

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DPMLibrary
Specifies a DPM library object that this cmdlet locks.
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

[Get-DPMLibrary](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMLibrary.md)

[Unlock-DPMLibraryDoor](xref:SystemCenter2016/DataProtectionManager/vlatest/Unlock-DPMLibraryDoor.md)

