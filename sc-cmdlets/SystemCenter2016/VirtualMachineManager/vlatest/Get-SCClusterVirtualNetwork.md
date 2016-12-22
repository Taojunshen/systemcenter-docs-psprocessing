---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DF682214-699F-4EEC-AF73-21B549EC4FC4
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCClusterVirtualNetwork.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCClusterVirtualNetwork.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCClusterVirtualNetwork.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCClusterVirtualNetwork

## SYNOPSIS
Gets the virtual network associated with a host cluster.

## SYNTAX

```
Get-SCClusterVirtualNetwork [-VMHostCluster] <HostCluster> [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCClusterVirtualNetwork** cmdlet gets one or more virtual networks associated with a host cluster.

## EXAMPLES

### Example 1: Get the virtual network for a cluster
```
PS C:\> $Cluster = Get-SCVMHostCluster -Name "VMHostCluster01.Contoso.com"
PS C:\> Get-SCClusterVirtualNetwork -VMHostCluster $Cluster
```

The first command gets the cluster object named VMHostCluster01 and stores the object in the $Cluster variable.

The second command gets the cluster virtual network object for the cluster stored in $Cluster (VMHostCluster01).

## PARAMETERS

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

### VirtualNetwork

## NOTES

## RELATED LINKS

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

