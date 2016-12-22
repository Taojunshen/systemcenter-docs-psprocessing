---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AED556EE-7B8E-432E-8140-338824A695CB
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMOnlineRecatalog.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMOnlineRecatalog.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMOnlineRecatalog.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-DPMOnlineRecatalog

## SYNOPSIS
Returns a detailed list of data for a DPM recovery point.

## SYNTAX

```
Start-DPMOnlineRecatalog [-RecoveryPoint] <RecoverySource> [-RecoveryPointLocation <RecoverySourceLocation>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMOnlineRecatalog** cmdlet returns details of data for a System Center 2016 - Data Protection Manager (DPM) recovery point.
You can use this information to perform partial recoveries or recovery of selected files.

## EXAMPLES

### Example 1: Start online catalog
```
PS C:\>$MPGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> $PObject = Get-DPMDatasource -ProtectionGroup $MPGroup
PS C:\> $RPoints = Get-DPMRecoveryPoint -Datasource $PObject
PS C:\> $RPLocation = Get-DPMRecoveryPointLocation -RecoveryPoint $RPoint
PS C:\> Start-DPMOnlineRecatalog -RecoveryPoint $RPoints[1] -RecoveryPointLocation $RPLocation
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to get a protection group for the DPM server named DPMServer07.
The command stores the protection group in the $MPGroup variable.

The second command uses the **Get-DPMDatasource** cmdlet to get a data source for the protection group in $MPGroup, and then stores that data source in the $PObject variable.

The third command uses the **Get-DPMRecoveryPoint** cmdlet to get recovery points for the data source in $PObject, and then stores those recovery points in the $RPoints variable.

The fourth command uses the **Get-DPMRecoveryPointLocation** cmdlet to get a recovery point location for the recovery point in $RPoint, and stores the recovery point location object in the $RPLocation variable.

The fifth command starts a catalog action for a recovery point in $RPoints.
The command uses standard array syntax to select the second member of that array.
The command specifies the recovery point location as the object in $RPLocation.

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

### -RecoveryPoint
Specifies a recovery point for which this cmdlet starts to catalog.
To obtain a recovery point object, use the Get-DPMRecoveryPoint cmdlet.

```yaml
Type: RecoverySource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointLocation
Specifies a recovery point location of the recovery points that this cmdlet gets.
To obtain a recovery point location object, use the Get-DPMRecoveryPointLocation cmdlet.
If a recovery item occurs in more than one recovery point, you must specify the location of recovery point.

```yaml
Type: RecoverySourceLocation
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

### Job

## NOTES

## RELATED LINKS

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPoint.md)

[Get-DPMRecoveryPointLocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMRecoveryPointLocation.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

