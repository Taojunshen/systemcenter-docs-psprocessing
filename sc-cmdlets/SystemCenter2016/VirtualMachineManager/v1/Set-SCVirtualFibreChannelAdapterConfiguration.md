---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualFibreChannelAdapterConfiguration.md
schema: 2.0.0
ms.assetid: EF12B578-9832-442D-9B05-6335EFB43E50
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualFibreChannelAdapterConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualFibreChannelAdapterConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualFibreChannelAdapterConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualFibreChannelAdapterConfiguration

## SYNOPSIS
Updates a configuration object that is used to configure an HBA object in a virtual machine configuration during virtual machine deployment.

## SYNTAX

```
Set-SCVirtualFibreChannelAdapterConfiguration [-PrimaryWorldWideNodeName <String>]
 [-PrimaryWorldWidePortName <String>] [-SecondaryWorldWideNodeName <String>]
 [-SecondaryWorldWidePortName <String>] [-StorageFabricClassification <StorageFabricClassification>]
 -VirtualFibreChannelAdapterConfiguration <VirtualFibreChannelAdapterConfiguration> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualFibreChannelAdapterConfiguration** cmdlet updates configuration objects that are used to configure a host bus adapter (HBA) object in a virtual machine configuration during virtual machine deployment.

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

### -PrimaryWorldWideNodeName
Specifies the primary world-wide node name for a virtual machine Virtual Fibre Channel adapter.

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

### -PrimaryWorldWidePortName
Specifies the primary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

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

### -SecondaryWorldWideNodeName
Specifies the secondary world-wide node name for a virtual machine Virtual Fibre Channel adapter.

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

### -SecondaryWorldWidePortName
Specifies the secondary world-wide port name for a virtual machine Virtual Fibre Channel adapter.

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

### -StorageFabricClassification
Specifies a classification for storage Fibre Channel fabric.

```yaml
Type: StorageFabricClassification
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualFibreChannelAdapterConfiguration
Specifies a configuration object to configure a virtual HBA object in a virtual machine configuration during a virtual machine deployment.

```yaml
Type: VirtualFibreChannelAdapterConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualFibreChannelAdapterConfiguration

## NOTES

## RELATED LINKS

[Get-SCVirtualFibreChannelAdapterConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualFibreChannelAdapterConfiguration.md)

