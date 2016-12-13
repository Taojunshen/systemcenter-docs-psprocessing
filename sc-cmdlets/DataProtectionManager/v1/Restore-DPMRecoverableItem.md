---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMDatasource.md
schema: 2.0.0
ms.assetid: 6CF7A85F-E5DE-4168-B8D0-DEF78E154425
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Restore-DPMRecoverableItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Restore-DPMRecoverableItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Restore-DPMRecoverableItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Restore-DPMRecoverableItem

## SYNOPSIS
Restores a version of the data source to a target location.

## SYNTAX

```
Restore-DPMRecoverableItem [-RecoveryOption] <RecoveryOptions> [[-RecoverableItem] <RecoverableObject[]>]
 [-RecoveryPointLocation <RecoverySourceLocation[]>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-RecoveryNotification <NotificationObject>]
 [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restore-DPMRecoverableItem** cmdlet recovers a point in time version of a recoverable item to the target location.
A recoverable item is a data source or a child recoverable item in a data source.

## EXAMPLES

### Example 1: Restore a version of a data source to a target location
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup[0]
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObjects[0] | Sort -Property RepresentedPointInTime -Descending | Select-Object -First 1
PS C:\> $ROption = New-DPMRecoveryOption -HyperVDatasource -TargetServer "HVDCenter02" -RecoveryLocation AlternateHyperVServer -RecoveryType Recover -TargetLocation "C:\VMRecovery"
PS C:\> Restore-DPMRecoverableItem -RecoverableItem $RPoint -RecoveryOption $ROption
```

This example restores a version of a nextref_virtualname data source to a recovery location.

The first command gets the protection group on the DPM server named DPMServer02, and then stores it in the $PGroup variable.

The second command gets the list of data sources for the first protection group in the $PGroup array.
The command stores the results in the $PObjects variable.

The third command gets the recovery point for the first data source in the $PObjects array, and then passes it to the **Sort-Object** cmdlet by using the pipe operator.
The **Sort-Object** cmdlet sorts the collection of recovery points in descending order of the date and time value of the **RepresentedPointInTime** property.
The **Select-Object** cmdlet selects the first recovery point from the collection, and then stores it in the $RPoint variable.
For more information, type `Get-Help Sort-Object` and `Get-Help Select-Object`.

The fourth command creates a recovery option for a nextref_virtualname data source on the server named HVDCenter02.
The command specifies AlternateHyperVServer as the recovery location and specifies that DPM stores the replica of the data source in C:\VMRecovery.
The command stores the recovery option in the $ROption variable.

The fifth command restores the data source in $RPoint by using the recovery option in $ROption.

## PARAMETERS

### -AdhocJobsContext
Specifies the context details of the ad hoc job.
Do not use this parameter from the Windows PowerShell command line.

```yaml
Type: AdhocJobsContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter and the *Async* parameter to build a graphical user interface based on cmdlets.
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

### -RecoverableItem
Specifies a recoverable item object.
This is a child item in a recovery point that is recoverable.
Examples include the following: a file system share or volume, a Microsoft SQL Server database, a Microsoft Exchange Server storage group, Microsoft SharePoint Site, Microsoft Virtual Machine, a Microsoft DPM database, system state or a recovery point.

```yaml
Type: RecoverableObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryNotification
Specifies that the recovery operation send a notification when the recovery operation finishes.
The **New-NotificationObject** cmdlet returns the notification object.

```yaml
Type: NotificationObject
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryOption
Specifies the recovery options for the data source.
You can use the New-DPMRecoveryOption cmdlet to create recovery options.

```yaml
Type: RecoveryOptions
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointLocation
Specifies an array of recovery point locations of recovery point that this cmdlet restores.
To obtain a recovery point location object, use the Get-DPMRecoveryPointLocation cmdlet.
If a recovery item exists in more than one recovery point, you must specify the location of a recovery point.

```yaml
Type: RecoverySourceLocation[]
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Get-DPMDatasource](xref:DataProtectionManager/v1/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMRecoverableItem](xref:DataProtectionManager/v1/Get-DPMRecoverableItem.md)

[Get-DPMRecoveryPoint](xref:DataProtectionManager/v1/Get-DPMRecoveryPoint.md)

[Get-DPMRecoveryPointLocation](xref:DataProtectionManager/v1/Get-DPMRecoveryPointLocation.md)

[New-DPMRecoveryOption](xref:DataProtectionManager/v1/New-DPMRecoveryOption.md)

[New-DPMRecoveryNotification](xref:DataProtectionManager/v1/New-DPMRecoveryNotification.md)

