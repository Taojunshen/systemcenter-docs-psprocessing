---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DB572B8E-1A8E-4C15-9067-EE39FE0AB254
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCComplianceScan.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCComplianceScan.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCComplianceScan.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCComplianceScan

## SYNOPSIS
Starts a compliance scan of a managed computer or host cluster.

## SYNTAX

### VMHostCluster
```
Start-SCComplianceScan [-VMMServer <ServerConnection>] -VMHostCluster <HostCluster> [-Baseline <Baseline>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### VMMManagedComputer
```
Start-SCComplianceScan [-VMMServer <ServerConnection>] [-Baseline <Baseline>]
 -VMMManagedComputer <VMMManagedComputer> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Start-SCComplianceScan cmdlet starts a compliance scan of a managed computer or host cluster.
During a compliance scan, the specified managed computer or host cluster is compared against assigned baselines, and the resulting compliance state is returned.

## EXAMPLES

### Example 1: Scan a host against a given baseline
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $Compliance = Get-SCComplianceStatus -VMMManagedComputer $VMHost.ManagedComputer
PS C:\> foreach($Bsc in $Compliance.BaselineLevelComplianceStatus)`
PS C:\> {if ($Bsc.Baseline.Name -eq "Security Baseline")`
PS C:\> {$Baseline = $Bsc.Baseline; break}}
PS C:\> Start-SCComplianceScan -VMMManagedComputer $VMHost.ManagedComputer -Baseline $Baseline
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the compliance status object for the host stored in $VMHost01 and stores the object in the $Compliance variable.

The next three lines use a **ForEach** statement to iterate through the baseline compliance status objects for the host.
If the baseline named Security Baseline is found, then the fifth command stores it in the $Baseline variable.

The last command starts the compliance scan on the host, using the baseline stored in $Baseline, which in this example is Security Baseline.

## PARAMETERS

### -Baseline
Specifies a VMM baseline object.

```yaml
Type: Baseline
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization (PRO) tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: VMHostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMManagedComputer
Specifies a computer object that is managed by VMM.

```yaml
Type: VMMManagedComputer
Parameter Sets: VMMManagedComputer
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
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

### ComplianceStatus

## NOTES

## RELATED LINKS

[Get-SCComplianceStatus](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComplianceStatus.md)

