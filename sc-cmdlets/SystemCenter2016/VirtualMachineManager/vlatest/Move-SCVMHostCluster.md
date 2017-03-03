---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3EE90116-0055-48B5-9644-BC337504B991
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Move-SCVMHostCluster

## SYNOPSIS
Moves a host cluster object managed by VMM from one host group to another.

## SYNTAX

```
Move-SCVMHostCluster [-VMHostCluster] <HostCluster> -ParentHostGroup <HostGroup> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Move-SCVMHostCluster** cmdlet moves a host cluster object managed by Virtual Machine Manager (VMM) from one host group to another.

You cannot use the **Move-SCVMHostCluster** cmdlet to move a VMware host cluster.
Instead, use vCenter Server to move a VMware host cluster.

## EXAMPLES

### Example 1: Move a specified host cluster to a new parent host group
```
PS C:\> $VMHostCluster = Get-SCVMHostCluster -Name "VMHostCluster01.Contoso.com"
PS C:\> $DestinationHG = Get-SCVMHostGroup -Name "Production"
PS C:\> Move-SCVMHostCluster -VMHostCluster $VMHostCluster -ParentHostGroup $DestinationHG
```

The first command gets the host cluster object named VMHostCluster01.Contoso.com and stores the object in the $VMHostCluster variable.

The second command gets the host group object named Production and stores the object in the $DestinationHG variable.

The last command moves host cluster VMHostCluster01.Contoso.com, stored in $VMHostCluster, from its current host group to the host group named Production, stored in $DestinationHG.

## PARAMETERS

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

### -ParentHostGroup
Specifies the parent host group that contains one or more hosts, host groups, or host clusters.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: ParentVMHostGroup

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

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMHostCluster
This cmdlet returns a **VMHostCluster** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

