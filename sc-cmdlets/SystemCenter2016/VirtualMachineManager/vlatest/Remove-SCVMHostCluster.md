---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7189867A-3310-4716-A502-FAA31C486939
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMHostCluster

## SYNOPSIS
Removes a host cluster object from VMM.

## SYNTAX

### NormalRemoval (Default)
```
Remove-SCVMHostCluster [-VMHostCluster] <HostCluster> [-Credential <VMMCredential>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ForceRemoval
```
Remove-SCVMHostCluster [-VMHostCluster] <HostCluster> [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMHostCluster** cmdlet removes one or more host cluster objects from Virtual Machine Manager (VMM).

**Remove-SCVMHostCluster** does not destroy the cluster.
To uncluster a host cluster by using VMM, use the Uninstall-SCVMHostCluster cmdlet.

## EXAMPLES

### Example 1: Remove a specific host cluster from VMM
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $Cluster = Get-SCVMHostCluster -Name "VMHostCluster01.Contoso.com"
PS C:\> Remove-SCVMHostCluster -VMHostCluster $Cluster -Credential $Credential -Confirm
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Credential variable.
The Run As account used for this operation must be a domain account with administrator rights on all of the nodes of the failover cluster that you want to remove.

The second command gets the failover cluster object named VMHostCluster01 and stores the object in the $VMHostCluster variable.

The last command removes the VMHostCluster01 cluster object from the VMM database and stops managing that host cluster, after prompting the user for confirmation.
It does not modify the host cluster settings or its existing virtual machines.
As this command is processed, $Credential provides the stored Run As account to **Remove-SCVMHostCluster**.

### Example 2: Remove all host clusters from VMM
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Get-SCVMHostCluster | Remove-SCVMHostCluster -Credential $Credential -Confirm
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $Credential variable.
The Run As account used for this operation must be a domain account with administrator rights on all of the nodes of the failover cluster that you want to remove.

The second command gets all host cluster objects and passes the objects to the **Remove-SCVMHostCluster** cmdlet, which removes each host cluster object from VMM and stops managing the corresponding host cluster, after prompting the user for confirmation.
The command does not modify the host cluster settings or its existing virtual machines.
As this command is processed, $Credential provides the stored Run As account to **Remove-SCVMHostCluster**.

## PARAMETERS

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

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the PSCredential object, type `Get-Help Get-Credential`.
For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: NormalRemoval
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: ForceRemoval
Aliases: 

Required: True
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

[Add-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHostCluster.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

