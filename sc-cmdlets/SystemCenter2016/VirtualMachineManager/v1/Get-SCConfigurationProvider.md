---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 5ba3aa13-3dac-4857-8109-5051b481872d
schema: 2.0.0
ms.assetid: 73FCAF9D-4990-45D0-A429-C8812769BD18
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCConfigurationProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCConfigurationProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCConfigurationProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCConfigurationProvider

## SYNOPSIS
Gets a configuration provider object.

## SYNTAX

### Default (Default)
```
Get-SCConfigurationProvider [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ByName
```
Get-SCConfigurationProvider [[-Name] <String>] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### ByType
```
Get-SCConfigurationProvider [[-ProviderType] <ConfigurationProviderType>] [-VMMServer <ServerConnection>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCConfigurationProvider** cmdlet gets a configuration provider object.
A configuration provider is a plug-in to Virtual Machine Manager (VMM) that translates VMM PowerShell commands to API calls that are specific to a type of load balancer or baseboard management controller.

## EXAMPLES

### Example 1: Get all configuration providers by a specified type
```
PS C:\>Get-SCConfigurationProvider -ProviderType "LoadBalancer"
```

This command gets all configuration providers that are load balancers.

### Example 2: Get a configuration provider by its name
```
PS C:\>$ConfigProvider = Get-SCConfigurationProvider -Name "Microsoft Network Load Balancing (NLB)"
PS C:\> $ConfigProvider
```

The first command gets the Microsoft Network Load Balancing (NLB) configuration provider by its name and stores it in the $ConfigProvider variable.

The second command displays information about the configuration provider stored in $ConfigProvider to the user.

## PARAMETERS

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProviderType
Specifies the type of a configuration provider.
Valid values are: LoadBalancer, OutOfBandManagement.

```yaml
Type: ConfigurationProviderType
Parameter Sets: ByType
Aliases: 
Accepted values: OutOfBandManagement, LoadBalancer, Gateway, VirtualSwitchExtensionManager, NetworkService, NetworkServiceV2, Unknown

Required: False
Position: 0
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

### ConfigurationProvider
This cmdlet returns a **ConfigurationProvider** object.

## NOTES

## RELATED LINKS

