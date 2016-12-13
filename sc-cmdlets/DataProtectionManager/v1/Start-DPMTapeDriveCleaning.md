---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMLibrary.md
schema: 2.0.0
ms.assetid: CC998B3C-D764-4AB2-A0F1-6410B8F9FB27
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeDriveCleaning.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeDriveCleaning.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMTapeDriveCleaning.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMTapeDriveCleaning

## SYNOPSIS
Starts a job to clean a tape drive.

## SYNTAX

```
Start-DPMTapeDriveCleaning [-TapeDrive] <Drive[]> [-JobStateChangedEventHandler <JobStateChangedEventHandler>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMTapeDriveCleaning** cmdlet starts a job to clean a tape drive.

## EXAMPLES

### Example 1: Clean a tape drive
```
PS C:\>$DpmLibrary = Get-DPMLibrary -DPMServerName "Contoso-DPMServer"
PS C:\> $DpmTapeDrive = Get-DPMTapeDrive -DPMLibrary $DPMLibrary
PS C:\> Start-DPMTapeDriveCleaning -TapeDrive $DpmTapeDrive
```

The first command uses the **Get-DPMLibrary** cmdlet to retrieve the library, and then stores it in the $DpmLibrary variable.

The second command uses the **Get-DPMTapeDrive** cmdlet to retrieve the tape drives in the library, and the stores the result in the $DpmTapeDrive variable.

The third command uses the **Start-DPMTapeDriveCleaning** cmdlet to clean the tape drive.

## PARAMETERS

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter to build a graphical user interface based on cmdlets.
Do not use this parameter in the System Center 2016 - Data Protection Manager (DPM) Management Shell.

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

### -TapeDrive
Specifies an array of tape drives.
This cmdlet cleans the drives that this parameter specifies.

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

### Job

## NOTES

## RELATED LINKS

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

