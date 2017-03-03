---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 07E141C9-14A7-4820-A6E0-6D7DAB8DD657
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCBaseline.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCBaseline.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCBaseline.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCBaseline

## SYNOPSIS
Modifies a baseline by adding or removing updates or assignment scopes.

## SYNTAX

```
Set-SCBaseline [-VMMServer <ServerConnection>] [-Baseline] <Baseline> [-Name <String>] [-Description <String>]
 [-AddUpdates <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]>]
 [-RemoveUpdates <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]>]
 [-AddAssignmentScope <IBaselineAssignmentScope>] [-RemoveAssignmentScope <IBaselineAssignmentScope>]
 [-JobGroup <Guid>] [-StartNow] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCBaseline** cmdlet modifies a baseline by adding or removing updates or assignment scopes.
A baseline is a list of updates which, together with scope assignments, can grade the compliance of required updates for Virtual Machine Manager (VMM) fabric servers.

## EXAMPLES

### Example 1: Modify an existing baseline by adding updates and an assignment scope
```
PS C:\> $Cluster = Get-SCVMHostCluster -Name "Cluster01"
PS C:\> $Baseline = Get-SCBaseline -Name "Security Baseline"
PS C:\> $Update = Get-SCUpdate -SecurityBulletinId "MS05-055"
PS C:\> Set-SCBaseline -Baseline $Baseline -AddUpdates $Update -AddAssignmentScope $Cluster
```

The first command gets the cluster object named Cluster01 and stores the object in the $Cluster variable.

The second command gets the baseline object named Security Baseline and stores the object in the $Baseline variable.

The third command gets the security bulletin update object named MS05-051 and stores the object in the $Update variable.

The last command adds the update stored in $Update (MS05-051) to the baseline stored in $Baseline (Security Baseline) and sets the assignment scope to the object stored in $Cluster (Cluster01).

### Example 2: Remove an update and an assignment scope from an existing baseline
```
PS C:\> $Cluster = Get-SCVMHostCluster -Name "Cluster01"
PS C:\> $Baseline = Get-SCBaseline -Name "Security Baseline"
PS C:\> $Update = Get-SCUpdate -SecurityBulletinId "MS05-055"
PS C:\> Set-SCBaseline -Baseline $Baseline -RemoveUpdates $Update -RemoveAssignmentScope $Cluster
```

The first command gets the cluster object named Cluster01 and stores the object in the $Cluster variable.

The second command gets the baseline object named Security Baseline and stores the object in the $Baseline variable.

The third command gets the security bulletin update object named MS05-051 and stores the object in the $Update variable.

The last command removes the update stored in $Update (MS05-051) from the baseline stored in $Baseline (Security Baseline) and removes the assignment scope stored in $Cluster (Cluster01).

## PARAMETERS

### -AddAssignmentScope
Specifies an array of virtual machine hosts or clusters that this cmdlet adds to a baseline assignment scope.

```yaml
Type: IBaselineAssignmentScope
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddUpdates
Specifies software updates to add to a baseline.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Baseline
Specifies a VMM baseline object.

```yaml
Type: Baseline
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
States a description for the specified object.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -Name
Specifies the name of a VMM object.

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
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

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

### -RemoveAssignmentScope
Specifies a scope.
This cmdlet removes one or more VMMManagedComputer, VMHostCluster, or VMHostGroup objects from a baseline assignment scope.

```yaml
Type: IBaselineAssignmentScope
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveUpdates
Specifies software updates to remove from a baseline.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SoftwareUpdate]
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

### -StartNow
Identifies the last command of a jobgroup and starts running the commands within the jobgroup.
This parameter must be used with the JobGroup parameter.

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

### Baseline
This cmdlet returns a **Baseline** object.

## NOTES

## RELATED LINKS

[Get-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCBaseline.md)

[Get-SCUpdate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdate.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[New-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCBaseline.md)

[Remove-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCBaseline.md)

