---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F97ECA21-7FC4-48E9-A51B-1C75DD1D9E55
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCClusterFunctionalLevel.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCClusterFunctionalLevel.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCClusterFunctionalLevel.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCClusterFunctionalLevel

## SYNOPSIS
Updates cluster functional level of a virtual machine host cluster or file server cluster.

## SYNTAX

### UpdateVMHostCluster
```
Update-SCClusterFunctionalLevel [-VMHostCluster] <HostCluster> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### UpdateStorageFileServerCluster
```
Update-SCClusterFunctionalLevel [-StorageFileServer] <StorageFileServer> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCClusterFunctionalLevel** cmdlet updates the cluster functional level of a Hyper-V host cluster or file server cluster.

## EXAMPLES

### Example 1: Update a host cluster
```
PS C:\> Get-SCVMHostCluster -Name "VMHostCluster03.Contoso.com" | Update-SCClusterFunctionalLevel
```

This command gets the host cluster that has the specified name by using the **Get-SCVMHostCluster** cmdlet.
The command passes that cluster to the current cmdlet by using the pipeline operator.
The current cmdlet updates the functional level of that cluster, and returns the updated **HostCluster** object.

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

### -StorageFileServer
Specifies a storage file server that this cmdlet updates.

```yaml
Type: StorageFileServer
Parameter Sets: UpdateStorageFileServerCluster
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a Virtual Machine Manager (VMM) host cluster that this cmdlet updates.

```yaml
Type: HostCluster
Parameter Sets: UpdateVMHostCluster
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

## NOTES

## RELATED LINKS

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

