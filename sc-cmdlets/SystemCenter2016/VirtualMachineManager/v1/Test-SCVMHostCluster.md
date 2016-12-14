---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostCluster.md
schema: 2.0.0
ms.assetid: 08580497-49A2-4CCB-AB67-EB270FF803ED
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Test-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCVMHostCluster

## SYNOPSIS
Validates whether hosts that are managed by VMM are suitable as nodes of a failover cluster.

## SYNTAX

### ValidateCluster
```
Test-SCVMHostCluster -VMHostCluster <HostCluster> [-Credential <VMMCredential>] [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ValidateNodes
```
Test-SCVMHostCluster -VMHost <Host[]> [-Credential <VMMCredential>] [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCVMHostCluster** cmdlet validates whether one or more hosts that are managed by Virtual Machine Manager (VMM) are suitable as a node of a failover cluster.

## EXAMPLES

### Example 1: Validate nodes to be clustered
```
PS C:\>$HostGroup = Get-SCVMHostGroup -Name "New York"
PS C:\> $Nodes = Get-SCVMHost | where {$_.Name -like "Cluster*" -and $_.VMHostGroup -eq $HostGroup} 
PS C:\> $Result = Test-SCVMHostCluster -VMHost $Nodes
PS C:\> Write-Output $Result.ValidationResult
PS C:\> Write-Output $Result.ResultFileLocation
```

The first command gets the host group object named New York in All Hosts and stores the object in the $HostGroup variable.

The second command gets all host objects with names beginning with "Cluster" from the New York host group and stores the objects in the $Nodes variable.

The third command validates the host objects stored in $Nodes for failover cluster creation and stores the results in $Result.

The fourth command displays the validation result to the user.

The last command displays the location of the validation report file to the user.

### Example 2: Validate an existing cluster
```
PS C:\>$Cluster = Get-SCVMHostCluster -Name "Cluster01"
PS C:\> $Result = Test-SCVMHostCluster -VMHostCluster $Cluster
PS C:\> Write-Output $Result.ValidationResult 
PS C:\> Write-Output $Result.ResultFileLocation
```

The first command gets the cluster object named Cluster01 and stores the object in the $Cluster variable.

The second command tests the cluster stored in $Cluster and stores the results of the test in $Result.

The third command displays the results for the user.

The last command displays the location of the validation report file for the user.

## PARAMETERS

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.
For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
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

### -VMHost
Specifies an array of virtual machine host objects.

```yaml
Type: Host[]
Parameter Sets: ValidateNodes
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: ValidateCluster
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

### ClusterValidationResult
This cmdlet returns a **ClusterValidationResult** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHostCluster.md)

[Get-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/v1/Uninstall-SCVMHostCluster.md)

