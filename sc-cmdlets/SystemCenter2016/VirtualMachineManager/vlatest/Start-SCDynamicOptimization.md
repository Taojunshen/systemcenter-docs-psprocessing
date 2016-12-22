---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 10FB402E-0F82-4EC8-B612-05D004F0AF54
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCDynamicOptimization.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCDynamicOptimization.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Start-SCDynamicOptimization.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCDynamicOptimization

## SYNOPSIS
Starts dynamic optimization on a host cluster or host group.

## SYNTAX

### ByHostGroup
```
Start-SCDynamicOptimization [-VMMServer <ServerConnection>] [-VMHostGroup] <HostGroup> [-WhatIf]
 [<CommonParameters>]
```

### ByHostCluster
```
Start-SCDynamicOptimization [-VMMServer <ServerConnection>] [-VMHostCluster] <HostCluster> [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCDynamicOptimization** cmdlet manully starts the dynamic optimization process for a host cluster or host group.

## EXAMPLES

### Example 1: Optimize hosts in a cluster
```
PS C:\> $Cluster = Get-SCVMHostCluster "Cluster01"
PS C:\> Start-SCDynamicOptimization -VMHostCluster $Cluster
```

The first command gets the host cluster object named Cluster01 and stores the object in the $Cluster variable.

The second command initiates the dynamic optimization process for the cluster stored in $Cluster.

### Example 2: Optimize hosts in a host group
```
PS C:\> $HostGroup = Get-SCVMHostGroup "HostGroup01"
PS C:\> Start-SCDynamicOptimization -VMHostGroup $HostGroup
```

The first command gets the host group object named HostGroup01 and stores the object in the $HostGroup variable.

The second command initiates the dynamic optimization process for the host group stored in $HostGroup.

## PARAMETERS

### -VMHostCluster
Specifies a Virtual Machine Manager (VMM) host cluster object.

```yaml
Type: HostCluster
Parameter Sets: ByHostCluster
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: ByHostGroup
Aliases: 

Required: True
Position: 0
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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DynamicOptimizationResults
This cmdlet returns a **DynamicOptimizationResults** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

