---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostFibreChannelVirtualSAN.md
schema: 2.0.0
ms.assetid: 4DC58061-9ADA-495C-B2FE-7823CD09A2A1
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostFibreChannelVirtualSAN.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostFibreChannelVirtualSAN.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMHostFibreChannelVirtualSAN.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
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

### 1:
```

```

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

[Get-SCVMHostFibreChannelVirtualSAN](xref:VirtualMachineManager/v1/Get-SCVMHostFibreChannelVirtualSAN.md)

[New-SCVMHostFibreChannelVirtualSAN](xref:VirtualMachineManager/v1/New-SCVMHostFibreChannelVirtualSAN.md)

[Set-SCVMHostFibreChannelVirtualSAN](xref:VirtualMachineManager/v1/Set-SCVMHostFibreChannelVirtualSAN.md)

