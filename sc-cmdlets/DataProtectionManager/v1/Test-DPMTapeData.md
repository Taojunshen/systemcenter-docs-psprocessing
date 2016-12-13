---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Copy-DPMTapeData.md
schema: 2.0.0
ms.assetid: 7BA43163-8D7B-4BDC-A0C1-22BCE86AFBFC
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Test-DPMTapeData.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Test-DPMTapeData.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Test-DPMTapeData.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-DPMTapeData

## SYNOPSIS
Verifies a data set for a recovery point.

## SYNTAX

```
Test-DPMTapeData [-RecoveryPoint] <RecoverySource> [-RecoveryPointLocation <RecoverySourceLocation>]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-DPMTapeData** cmdlet verifies a data set for a recovery point in System Center 2016 - Data Protection Manager (DPM).
A recovery point is a point-in-time copy of a replica stored on a DPM server.

## EXAMPLES

### Example 1: Verify a recovery point
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> $PObject = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> $RPoints = Get-DPMRecoveryPoint -Datasource $PObject
PS C:\> $RPLocation = Get-DPMRecoveryPointLocation -RecoveryPoint $RPoints[1]
PS C:\> Test-DPMTapeData -RecoveryPoint $RPoints[1] -RecoveryPointLocation $RPLocation
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to retrieve the protection group on the DPM server.
The command stores the result in the $PGroup variable.

The second command uses the **Get-DPMDatasource** cmdlet to retrieve the data source for the protection group.
The command stores the result in the variable named $PObject.

The third command uses the **Get-DPMRecoveryPoint** cmdlet to retrieve recovery points for the data source.
The command stores the result in the variable named $RPoints.

The fourth command uses the **Get-DPMRecoveryPointLocation** cmdlet to retrieve the recovery point location for a point in $RPoints.
The command stores the result in the variable named $RPLocation.

The final command uses the **Test-DPMTapeData** cmdlet to verify a data set for the second recovery point.

## PARAMETERS

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

### -RecoveryPoint
Specifies the recovery point for which this cmdlet verifies a data set.

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
Specifies the location of a recovery point that this cmdlet tests.
To obtain a recovery point location object, use the Get-DPMRecoveryPointLocation cmdlet.
A recovery item may exist in more than one location for the same point in time, such as on a disk and tape, or on two separate tapes.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RecoveryPoint

## NOTES

## RELATED LINKS

[Copy-DPMTapeData](xref:DataProtectionManager/v1/Copy-DPMTapeData.md)

[Get-DPMDatasource](xref:DataProtectionManager/v1/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMRecoveryPoint](xref:DataProtectionManager/v1/Get-DPMRecoveryPoint.md)

[Get-DPMDatasource](xref:DataProtectionManager/v1/Get-DPMDatasource.md)

