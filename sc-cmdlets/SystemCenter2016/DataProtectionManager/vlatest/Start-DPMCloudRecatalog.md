---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 649F94AA-8AA3-4E16-AED1-7B412C3639E6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMCloudRecatalog.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMCloudRecatalog.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMCloudRecatalog.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-DPMCloudRecatalog

## SYNOPSIS
Recatalogs a cloud recovery point.

## SYNTAX

```
Start-DPMCloudRecatalog [-RecoverableItem] <RecoverableObject[]>
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-RecoveryNotification <NotificationObject>]
 [-AdhocJobsContext <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMCloudRecatalog** cmdlet starts to recatalog a point in time version of a System Center 2016 - Data Protection Manager (DPM) cloud recovery point.

## EXAMPLES

### Example 1: Recatalog a version of a cloud recovery point
```
PS C:\>$RPoints = Get-DPMProtectionGroup | Where {$_.Name -like "ProtectionGroup06"} | Get-DPMDatasource | Get-DPMRecoveryPoint -Online
PS C:\> Start-CloudRecatalog -RecoverableItem $RPoints[1]
```

The first command gets a protection group by using the **Get-DPMProtectionGroup** cmdlet.
That cmdlet gets all protection groups, and then passes them to the **Where-Object** cmdlet by using the pipeline operator.
That cmdlet drops all groups that do not match its criteria.
For more information, type `Get-Help Where-Object`.

The command then passes the protection group to the **Get-DPMDatasource** cmdlet, which gets the data sources for that protection group.

The command then passes the data source to the **Get-DPMRecoveryPoint** cmdlet, which gets all available recovery points for the data source.
The command stores the recovery points in the $RPoints variable.

The second command starts to recatalog the version of a cloud recovery point stored in position one (1) of $RPoints.

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

### -RecoverableItem
Specifies a recoverable item object.
This is a child item in a recovery point that is recoverable.
For example, a file system share or volume, a Microsoft SQL Server database, a Microsoft Exchange Server storage group, Microsoft SharePoint, Microsoft Virtual Machine, a Microsoft DPM database, system state, or a recovery point.

```yaml
Type: RecoverableObject[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryNotification
Specifies a notification to send when recovery is finished.
You can use the New-DPMRecoveryNotification cmdlet to create a notification object.

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

[Start-DPMCreateCatalog](xref:SystemCenter2016/DataProtectionManager/vlatest/Start-DPMCreateCatalog.md)

[New-DPMRecoveryNotification](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMRecoveryNotification.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

