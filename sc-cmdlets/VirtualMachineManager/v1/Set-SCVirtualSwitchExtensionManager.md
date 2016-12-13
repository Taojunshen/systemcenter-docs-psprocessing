---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVirtualSwitchExtensionManager.md
schema: 2.0.0
ms.assetid: 6DDF7536-6C21-4F4D-8218-5E65F7E11DE4
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVirtualSwitchExtensionManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVirtualSwitchExtensionManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVirtualSwitchExtensionManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualSwitchExtensionManager

## SYNOPSIS
Sets the properties of a virtual switch extension manager.

## SYNTAX

```
Set-SCVirtualSwitchExtensionManager [-VMMServer <ServerConnection>]
 [-VirtualSwitchExtensionManager] <NetworkServiceBase>
 [-VirtualSwitchExtensionManagerConnectionString <String>] [-Manufacturer <String>] [-Model <String>]
 [-RunAsAccount <RunAsAccount>] [-ConfigurationProvider <ConfigurationProvider>]
 [-AddVMHostGroup <HostGroup[]>] [-RemoveVMHostGroup <HostGroup[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualSwitchExtensionManager** cmdlet updates the properties of a virtual switch extension manager.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AddVMHostGroup
Specifies an array of host groups that this cmdlet adds to an existing host group array or private cloud.

```yaml
Type: HostGroup[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationProvider
Specifies a configuration provider object.

A configuration provider is a plug-in to VMM that translates VMM PowerShell commands to API calls that are specific to a type of load balancer.
If no configuration provider is specified, VMM uses the Manufacturer and Model information to choose an available configuration provider.
If no configuration provider is found, the load balancer is not added.

```yaml
Type: ConfigurationProvider
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

### -Manufacturer
Specifies the name of the company that manufactured a physical device.
The acceptable values for this parameter are:

- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
- Single quote (')

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

### -Model
Specifies the model of a physical device.

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

### -RemoveVMHostGroup
Specifies one or more host groups from a host group array or private cloud to remove.

```yaml
Type: HostGroup[]
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
Type: NetworkServiceBase
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

## NOTES

## RELATED LINKS

[Add-SCVirtualSwitchExtensionManager](xref:VirtualMachineManager/v1/Add-SCVirtualSwitchExtensionManager.md)

[Get-SCVirtualSwitchExtensionManager](xref:VirtualMachineManager/v1/Get-SCVirtualSwitchExtensionManager.md)

[Read-SCVirtualSwitchExtensionManager](xref:VirtualMachineManager/v1/Read-SCVirtualSwitchExtensionManager.md)

[Remove-SCVirtualSwitchExtensionManager](xref:VirtualMachineManager/v1/Remove-SCVirtualSwitchExtensionManager.md)

[Test-SCVirtualSwitchExtensionManager](xref:VirtualMachineManager/v1/Test-SCVirtualSwitchExtensionManager.md)

