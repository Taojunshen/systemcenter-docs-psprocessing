---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostNetworkAdapter.md
schema: 2.0.0
ms.assetid: 6BD9E82B-72EF-4374-A6EB-01B6176BF266
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMHostNetworkAdapter

## SYNOPSIS
Removes a physical host network adapter object from a virtual network that is configured on a host managed by VMM.

## SYNTAX

```
Remove-SCVMHostNetworkAdapter [-VirtualNetwork] <VirtualNetwork> -VMHostNetworkAdapter <HostNetworkAdapter>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMHostNetworkAdapter** cmdlet removes one or more physical host network adapter objects from a virtual network that is configured on a host managed by Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove the physical host network adapter from a specific virtual network
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com" 
PS C:\> $HostAdapter = Get-SCVMHostNetworkAdapter -VMHost $VMHost -Name "HostAdapter01"
PS C:\> $VirtualNetwork = Get-SCVirtualNetwork -VMHost $VMHost -Name "ExternalVirtualNetwork01"
PS C:\> Remove-SCVMHostNetworkAdapter -VMHostNetworkAdapter $HostAdapter -VirtualNetwork $VirtualNetwork -Confirm
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the host network adapter object named HostAdapter01 and stores the object in the $HostAdapter variable.

The third command gets the virtual network object named ExternalVirtualNetwork01 from VMHost01 and stores the object in the $VirtualNetwork variable.

The last command removes the host network adapter stored in $HostAdapter from the virtual network stored in $VirtualNetwork.
The Confirm parameter prompts you to confirm whether you want to delete the adapter from VMM.

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

### -VMHostNetworkAdapter
Specifies a physical network adapter object on a host to which virtual machines deployed on that host can connect. 



Example format: `-VMHostNetworkAdapter $VMHostNIC`

```yaml
Type: HostNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Specifies a virtual network object.

```yaml
Type: VirtualNetwork
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

[Add-SCVMHostNetworkAdapter](xref:VirtualMachineManager/v1/Add-SCVMHostNetworkAdapter.md)

[Get-SCVirtualNetwork](xref:VirtualMachineManager/v1/Get-SCVirtualNetwork.md)

[Get-SCVMHost](xref:VirtualMachineManager/v1/Get-SCVMHost.md)

[Get-SCVMHostNetworkAdapter](xref:VirtualMachineManager/v1/Get-SCVMHostNetworkAdapter.md)

[Set-SCVMHostNetworkAdapter](xref:VirtualMachineManager/v1/Set-SCVMHostNetworkAdapter.md)

