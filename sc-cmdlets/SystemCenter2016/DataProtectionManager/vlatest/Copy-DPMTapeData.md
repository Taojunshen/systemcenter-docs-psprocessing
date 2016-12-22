---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 93FCF1EA-5FA6-469D-9729-4F8848700F74
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Copy-DPMTapeData.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Copy-DPMTapeData.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Copy-DPMTapeData.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Copy-DPMTapeData

## SYNOPSIS
Copies the recovery point data from a tape.

## SYNTAX

### DumpMediaHeadlessDataset
```
Copy-DPMTapeData [-DPMServerName <String>] -IncompleteDataset <HeadlessDataset> -Tape <Media> [-Restore]
 -OverwriteType <OverwriteType> [-RecreateReparsePoint] [-RestoreSecurity] -TargetServer <String>
 -TargetPath <String> [-RecoveryNotification <NotificationObject>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DumpMediaRecoveryPoint
```
Copy-DPMTapeData [-RecoveryPoint] <RecoverySource> [-RecoveryPointLocation <RecoverySourceLocation>]
 [-AdhocJobsContext <AdhocJobsContext>] -Tape <Media> [-Restore] -OverwriteType <OverwriteType>
 [-RecreateReparsePoint] [-RestoreSecurity] -TargetServer <String> -TargetPath <String>
 [-RecoveryNotification <NotificationObject>] [-JobStateChangedEventHandler <JobStateChangedEventHandler>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CopyToMedia
```
Copy-DPMTapeData [-RecoveryPoint] <RecoverySource> -SourceLibrary <Library> -TargetLibrary <Library>
 -TapeLabel <String> -TapeOption <TapeOptions> [-RecoveryPointLocation <RecoverySourceLocation>]
 [-AdhocJobsContext <AdhocJobsContext>] [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Copy-DPMTapeData** cmdlet copies the recovery point data from a tape in System Center 2016 - Data Protection Manager (DPM).

## EXAMPLES

## PARAMETERS

### -AdhocJobsContext
Specifies the context details of the ad hoc job.
Do not use this parameter from the Windows PowerShell command line.

```yaml
Type: AdhocJobsContext
Parameter Sets: DumpMediaRecoveryPoint, CopyToMedia
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: DumpMediaHeadlessDataset
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncompleteDataset
Indicates that the operation occurs only on the portion of the data present on the current tape.
In some situations, data spans multiple tapes.

```yaml
Type: HeadlessDataset
Parameter Sets: DumpMediaHeadlessDataset
Aliases: 

Required: True
Position: Named
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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OverwriteType
Specifies the action that DPM takes when the file that it is recovering already exists.

The acceptable values for this parameter are:

- CreateCopy 
- Skip
- Overwrite

```yaml
Type: OverwriteType
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 
Accepted values: Overwrite, NoOverwrite, CopyOnExist

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryNotification
Specifies that the recovery operation send a notification when the recovery operation finishes.
The [New-NotificationObject](./New-NotificationObject.md) cmdlet returns the notification object.

```yaml
Type: NotificationObject
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPoint
Specifies a recovery point that this cmdlet copies.
To obtain a recovery point location object, use the [Get-DPMRecoveryPoint](./Get-DPMRecoveryPoint.md) cmdlet.

```yaml
Type: RecoverySource
Parameter Sets: DumpMediaRecoveryPoint, CopyToMedia
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointLocation
Specifies the location of a recovery point that this cmdlet copies.
To obtain a recovery point location object, use the [Get-DPMRecoveryPointLocation](./Get-DPMRecoveryPointLocation.md) cmdlet.
A recovery item may exist in more than one location for the same time, such as on a disk and tape, or on two separate tapes.

```yaml
Type: RecoverySourceLocation
Parameter Sets: DumpMediaRecoveryPoint, CopyToMedia
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecreateReparsePoint
Indicates that the cmdlet recreates the reparse point.

```yaml
Type: SwitchParameter
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Restore
Indicates that the cmdlet performs a restore operation.

```yaml
Type: SwitchParameter
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreSecurity
Indicates that DPM uses the security settings of the recovery point during a restore operation.
When you specify the *RestoreSecurity* parameter, the cmdlet uses the security settings from the recovery point.
Otherwise, the cmdlet uses the security settings of the destination server.

```yaml
Type: SwitchParameter
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceLibrary
Specifies the location of a dataset to copy.

```yaml
Type: Library
Parameter Sets: CopyToMedia
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tape
Specifies a tape from which this cmdlet copies a recovery point.
To obtain a **Tape** object, use the **Get-DPMTape** cmdlet.

```yaml
Type: Media
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TapeLabel
Specifies a label that identifies the tape.

```yaml
Type: String
Parameter Sets: CopyToMedia
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TapeOption
Specifies that the copy operation compress or encrypt the data on the tape.

The acceptable values for this parameter are:
- 0 Compress
- 1 Encrypt
- 2 NoCompressAndNoEncrypt

```yaml
Type: TapeOptions
Parameter Sets: CopyToMedia
Aliases: 
Accepted values: Compress, Encrypt, NoCompressAndNoEncrypt

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetLibrary
Specifies the target library to which to copy the data set.

```yaml
Type: Library
Parameter Sets: CopyToMedia
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPath
Specifies a target path.

```yaml
Type: String
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetServer
Specifies the target server for recovery.

If you use this cmdlet in a clustered environment, specify the target server parameter in the format ResourceGroupName.ClusterName.DomainName.

```yaml
Type: String
Parameter Sets: DumpMediaHeadlessDataset, DumpMediaRecoveryPoint
Aliases: 

Required: True
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

### Job

## NOTES

## RELATED LINKS

[Get-DPMTape](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMTape.md)

[Test-DPMTapeData](xref:SystemCenter2016/DataProtectionManager/vlatest/Test-DPMTapeData.md)
