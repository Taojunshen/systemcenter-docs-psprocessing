---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostCluster.md
schema: 2.0.0
ms.assetid: 6C0CDD3F-AE44-4718-8624-307F2ACFB81E
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVMHostCluster

## SYNOPSIS
Refreshes host cluster properties in the VMM console.

## SYNTAX

```
Read-SCVMHostCluster [-VMHostCluster] <HostCluster> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVMHostCluster** cmdlet refreshes host cluster properties so that the Virtual Machine Manager (VMM) console displays updated information about the host cluster.

## EXAMPLES

### Example 1: Refresh information about a specific host cluster
```
PS C:\>Get-SCVMHostCluster -Name "VMHostCluster01.Contoso.Com" | Read-SCVMHostCluster
```

This command gets the host cluster object named VMHostCluster01 and passes the object to the **Refresh-SCVMHostCluster** cmdlet, which refreshes the properties for the host cluster so that current information about the host cluster appears in the VMM console.

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

[Move-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:SystemCenter2016/VirtualMachineManager/vlatest/Uninstall-SCVMHostCluster.md)

