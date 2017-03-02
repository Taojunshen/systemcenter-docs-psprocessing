---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4DC58061-9ADA-495C-B2FE-7823CD09A2A1
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostFibreChannelVirtualSAN.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostFibreChannelVirtualSAN.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostFibreChannelVirtualSAN.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCVMHostFibreChannelVirtualSAN

## SYNOPSIS
Removes a Fibre Channel SAN from Hyper-V.

## SYNTAX

```
Remove-SCVMHostFibreChannelVirtualSAN [-HostFibreChannelVirtualSAN] <HostFibreChannelVirtualSAN>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMHostFibreChannelVirtualSAN** cmdlet removes a Fibre Channel storage area network (SAN) from Hyper-V.

## EXAMPLES


## PARAMETERS

### -HostFibreChannelVirtualSAN
Specifies a host Fibre Channel virtual SAN object.

```yaml
Type: HostFibreChannelVirtualSAN
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMHostFibreChannelVirtualSAN
This cmdlet returns an **SCVMHostFibreChannelVirtualSAN** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostFibreChannelVirtualSAN.md)

[New-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostFibreChannelVirtualSAN.md)

[Set-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostFibreChannelVirtualSAN.md)

