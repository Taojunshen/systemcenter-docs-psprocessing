---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMHostFibreChannelHba.md
schema: 2.0.0
ms.assetid: 58A13324-89B1-4382-B300-730DC4B68CB6
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostFibreChannelVirtualSAN.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostFibreChannelVirtualSAN.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCVMHostFibreChannelVirtualSAN.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMHostFibreChannelVirtualSAN

## SYNOPSIS
Creates a virtual Fibre Channel SAN object on a Hyper-V host.

## SYNTAX

```
New-SCVMHostFibreChannelVirtualSAN -Name <String> [-Description <String>]
 [-HostFibreChannelHba <HostFibreChannelHba[]>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHostFibreChannelVirtualSAN** cmdlet creates a virtual Fibre Channel storage area network (SAN) object on a Hyper-V host.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Description
Specifies a description for the virtual SAN object.

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

### -HostFibreChannelHba
Specifies an array of host Fibre Channel HBA objects.

To obtain a Fibre Channel HBA object, use the Get-SCVMHostFibreChannelHba cmdlet.

```yaml
Type: HostFibreChannelHba[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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
This cmdlet returns a **VMHostFibreChannelVirtualSAN** object.

## NOTES

## RELATED LINKS

[Get-SCVMHostFibreChannelHba](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostFibreChannelHba.md)

[Get-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHostFibreChannelVirtualSAN.md)

[Remove-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHostFibreChannelVirtualSAN.md)

[Set-SCVMHostFibreChannelVirtualSAN](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHostFibreChannelVirtualSAN.md)

