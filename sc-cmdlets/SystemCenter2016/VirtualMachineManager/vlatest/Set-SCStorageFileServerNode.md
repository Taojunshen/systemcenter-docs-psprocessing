---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F1CFD7CF-A42E-4283-AA96-382A3205F01A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServerNode.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServerNode.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFileServerNode.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageFileServerNode

## SYNOPSIS
Modifies a file server node.

## SYNTAX

```
Set-SCStorageFileServerNode [-StorageFileServerNode] <StorageFileServerNode> [-BMCAddress <String>]
 [-BMCRunAsAccount <RunAsAccount>] [-BMCPort <UInt32>] [-BMCProtocol <OutOfBandManagementType>]
 [-BMCCustomConfigurationProvider <ConfigurationProvider>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageFileServerNode** cmdlet modifies a file server node.

## EXAMPLES


## PARAMETERS

### -BMCAddress
Specifies, or updates, the out-of-band baseboard management controller (BMC) address for a specific physical machine.
This might be an IP address, the fully qualified domain name (FQDN), or the DNS prefix (which is usually the same name as the NetBIOS name).

Typically, the BMC address and its connection to the network are separate from the IP address associated with a standard network adapter.
Alternatively, some computers do use a standard network adapter to provide a single address for the BMC and for the network adapter.
However, the BMC address has a unique port and is thus uniquely identifiable on the network.

- Example IPv4 format:       `-BMCAddress "10.0.0.21"`
- Example Ipv6 format:       `-BMCAddress "2001:4898:2a:3:657b:9c7a:e1f0:6829"`
- Example FQDN format:       `-BMCAddress "Computer01.Contoso.com"`
- Example NetBIOS format:    `-BMCAddress "Computer01"`

Note: By default, VMM uses an IP address or FQDN for the BMCAddress.
However, it is also possible to create a Windows PowerShell module that enables you to specify other types of addresses as the BMC address.

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

### -BMCCustomConfigurationProvider
Specifies, or updates, a configuration provider object for a baseboard management controller (BMC).
A configuration provider is a plug-in to VMM that translates VMM PowerShell commands to API calls that are specific to a type of baseboard management controller.
You should use this parameter with the Custom BMCProtocol.

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

### -BMCPort
Specifies, or updates, the out-of-band baseboard management controller (BMC) port for a specific physical machine.
A BMC port is also known as a service processor port.
Example default ports are 623 for IPMI and 443 for SMASH over WS-Man.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCProtocol
Specifies, or updates, the protocol that VMM uses to communicate with the out-of-band baseboard management controller (BMC).
Valid values are: IPMI, SMASH, Custom.

A BMC (also known as a service processor or management controller) is a specialized controller on the motherboard of a server that acts an interface between the hardware and system management software.
If the motherboard of a physical machine includes a BMC, when the machine is plugged in (whether it is powered off or powered on, and whether or not an operating system is installed), information about system hardware and the state of that system hardware health is available.

Example format: `-BMCProtocol "Custom"`

Note: The Custom protocol requires that you use the *BMCCustomConfigurationProvider* parameter.

```yaml
Type: OutOfBandManagementType
Parameter Sets: (All)
Aliases: 
Accepted values: None, IPMI, SMASH, Custom

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BMCRunAsAccount
Specifies the Run As account to use with the baseboard management controller (BMC) device.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -StorageFileServerNode
Specifies an array of storage file server node objects.

```yaml
Type: StorageFileServerNode
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

