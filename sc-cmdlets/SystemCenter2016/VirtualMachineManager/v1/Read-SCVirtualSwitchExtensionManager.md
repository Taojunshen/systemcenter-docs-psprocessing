---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVirtualSwitchExtensionManager.md
schema: 2.0.0
ms.assetid: 38F2CC11-C926-4A50-AC36-890A5E35AB79
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCVirtualSwitchExtensionManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCVirtualSwitchExtensionManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCVirtualSwitchExtensionManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVirtualSwitchExtensionManager

## SYNOPSIS
Refreshes a virtual switch extension manager.

## SYNTAX

```
Read-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [-VirtualSwitchExtensionManager] <VirtualSwitchExtensionManager> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVirtualSwitchExtensionManager** cmdlet refreshes a virtual switch extension manager.

## EXAMPLES

### 1:
```

```

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

### -VirtualSwitchExtensionManager
Specifies a virtual switch extension manager object.
To obtain a virtual switch extension manager object, use the Get-SCVirtualSwitchExtensionManager cmdlet.

```yaml
Type: VirtualSwitchExtensionManager
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

## NOTES

## RELATED LINKS

[Add-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVirtualSwitchExtensionManager.md)

[Get-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualSwitchExtensionManager.md)

[Remove-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVirtualSwitchExtensionManager.md)

[Set-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualSwitchExtensionManager.md)

[Test-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/v1/Test-SCVirtualSwitchExtensionManager.md)

