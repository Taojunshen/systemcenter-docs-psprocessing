---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./DataProtectionManager.md
schema: 2.0.0
ms.assetid: C5CF0A11-7BA6-41FD-8C98-527A763FEE02
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMLibraryRescan.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMLibraryRescan.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Start-DPMLibraryRescan.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMLibraryRescan

## SYNOPSIS
Starts a scan to identify new libraries and update existing libraries.

## SYNTAX

### Full (Default)
```
Start-DPMLibraryRescan [[-DPMServerName] <String>] [-Full]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [<CommonParameters>]
```

### Quick
```
Start-DPMLibraryRescan [[-DPMServerName] <String>] [-Quick]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [<CommonParameters>]
```

### RefreshOnly
```
Start-DPMLibraryRescan [[-DPMServerName] <String>] [-RefreshOnly]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMLibraryRescan** cmdlet starts a scan for a System Center 2016 - Data Protection Manager (DPM) server to identify new libraries and stand-alone tape drives, and to update information for existing libraries.
You can select one of the following parameters: 

- *Full*.
The cmdlet checks for new libraries and stand-alone tape drives and refreshes all libraries and drives. 
- *Quick*.
The cmdlet checks for new libraries and stand-alone tape drives. 
- *RefreshOnly*.
The cmdlet refreshes known drives. 

If you do not specify any of these parameters, the cmdlet performs a full scan.

## EXAMPLES

### Example 1: Perform a full rescan
```
PS C:\>Start-DPMLibraryRescan -DPMServerName "DPMServer07" -Full
```

This command starts a full rescan of the libraries on the DPMserver named DPMServer07.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server that this cmdlet scans.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Full
Indicates that the cmdlet starts a full library rescan.

```yaml
Type: SwitchParameter
Parameter Sets: Full
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
Aliases: Handler

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quick
Indicates that the cmdlet starts a quick library rescan.

```yaml
Type: SwitchParameter
Parameter Sets: Quick
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RefreshOnly
Indicates that the cmdlet starts a refresh library scan.

```yaml
Type: SwitchParameter
Parameter Sets: RefreshOnly
Aliases: 

Required: True
Position: Named
Default value: None
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

[Data Protection Manager Cmdlets](xref:DataProtectionManager/v1/DataProtectionManager.md)

