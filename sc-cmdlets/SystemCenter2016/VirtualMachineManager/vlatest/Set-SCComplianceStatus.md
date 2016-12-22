---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C5D10ECB-7163-47BF-9470-77E78198F16F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComplianceStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComplianceStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComplianceStatus.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCComplianceStatus

## SYNOPSIS
Sets a compliance status object.

## SYNTAX

### Default (Default)
```
Set-SCComplianceStatus [-VMMServer <ServerConnection>] [-ComplianceStatus] <ComplianceStatus>
 -Baseline <Baseline> -Update <SoftwareUpdate> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### AddExemption
```
Set-SCComplianceStatus [-VMMServer <ServerConnection>] [-ComplianceStatus] <ComplianceStatus>
 -Baseline <Baseline> -Update <SoftwareUpdate> [-ExemptionNote <String>] [-AddExemption] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### RemoveExemption
```
Set-SCComplianceStatus [-VMMServer <ServerConnection>] [-ComplianceStatus] <ComplianceStatus>
 -Baseline <Baseline> -Update <SoftwareUpdate> [-RemoveExemption] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCComplianceStatus** cmdlet sets a compliance status object.

## EXAMPLES

### Example 1: Add an exemption to a compliance status
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $Compliance = Get-SCComplianceStatus -VMMManagedComputer $VMHost.ManagedComputer
PS C:\> $Baseline = Get-SCBaseline -Name "Security Baseline"
PS C:\> $Update = Get-SCUpdate -SecurityBulletinID "MS05-055"
PS C:\> Set-SCComplianceStatus -ComplianceStatus $Compliance -Baseline $Baseline -Update $Update -AddExemption -ExemptionNote "This exemption has been signed off by the IT Manager."
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the compliance status for VMHost01 and stores the staus object in the $Compliance variable.

The third command gets the baseline named Security Baseline and stores the object in the $Baseline variable.

The fourth command gets the security bulletin update MS05-055 and stores the update object in the $Update variable.

The last command adds an exemption to the update MS05-055 that is part of the Security Baseline baseline, and an exemption note with a business reason for the exemption.

## PARAMETERS

### -AddExemption
Specifies an exemption to an update that is part of a baseline that this cmdlet adds.

```yaml
Type: SwitchParameter
Parameter Sets: AddExemption
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Baseline
Specifies a Virtual Machine Manager (VMM) baseline object.

```yaml
Type: Baseline
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComplianceStatus
Specifies a compliance status object.
The compliance status of an object indicates the object's compliance to the baselines to which the object is assigned.

```yaml
Type: ComplianceStatus
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ExemptionNote
Specifies a business reason for the exempted update.

```yaml
Type: String
Parameter Sets: AddExemption
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### -RemoveExemption
Specifies an exemption from an update that is part of a baseline that this   cmdlet removes.

```yaml
Type: SwitchParameter
Parameter Sets: RemoveExemption
Aliases: 

Required: True
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

### -Update
Specifies a software update object.

```yaml
Type: SoftwareUpdate
Parameter Sets: (All)
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
This cmdlet returns a **ComplianceStatus** object.

## NOTES

## RELATED LINKS

[Get-SCComplianceStatus](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComplianceStatus.md)

