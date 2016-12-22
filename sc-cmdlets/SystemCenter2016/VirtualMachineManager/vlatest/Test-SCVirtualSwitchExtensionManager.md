---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 68B2450D-6055-44F1-B766-3148A73B4AAA
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualSwitchExtensionManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualSwitchExtensionManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCVirtualSwitchExtensionManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCVirtualSwitchExtensionManager

## SYNOPSIS
Tests a virtual switch extension manager.

## SYNTAX

```
Test-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [-VirtualSwitchExtensionManagerConnectionString] <String> -ConfigurationProvider <ConfigurationProvider>
 -RunAsAccount <RunAsAccount> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCVirtualSwitchExtensionManager** cmdlet tests a virtual switch extension manager.

## EXAMPLES


## PARAMETERS

### -ConfigurationProvider
Specifies a configuration provider object.

A configuration provider is a plug-in to VMM that translates VMM PowerShell commands to API calls that are specific to a type of load balancer.
If no configuration provider is specified, VMM uses the Manufacturer and Model information to choose an available configuration provider.
If no configuration provider is found, the load balancer is not added.

```yaml
Type: ConfigurationProvider
Parameter Sets: (All)
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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: True
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

### -VirtualSwitchExtensionManagerConnectionString
Specifies the information required to connect to the virtual switch extension manager.

```yaml
Type: String
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

[Add-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVirtualSwitchExtensionManager.md)

[Get-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualSwitchExtensionManager.md)

[Read-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualSwitchExtensionManager.md)

[Remove-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualSwitchExtensionManager.md)

[Set-SCVirtualSwitchExtensionManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualSwitchExtensionManager.md)

