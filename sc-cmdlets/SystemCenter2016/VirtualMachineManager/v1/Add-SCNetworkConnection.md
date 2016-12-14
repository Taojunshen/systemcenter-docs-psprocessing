---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCNetworkConnection.md
schema: 2.0.0
ms.assetid: 2E5555DC-0C6E-496F-BE51-BA7AAFF2E4A1
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCNetworkConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCNetworkConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCNetworkConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCNetworkConnection

## SYNOPSIS
Adds a network service connection.

## SYNTAX

### AddNetworkServiceConnectionByLND
```
Add-SCNetworkConnection [-VMMServer <ServerConnection>] [-Service] <NetworkService>
 -LogicalNetworkDefinition <LogicalNetworkDefinition> [-IPv4Address <String>] [-IPv6Address <String>]
 [-Description <String>] -Name <String> [-ConnectionType <NetworkConnectionType>]
 [-NetworkAdapter <NetworkServiceAdapterInfo>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### AddNetworkServiceConnectionByVMSubnet
```
Add-SCNetworkConnection [-VMMServer <ServerConnection>] [-Service] <NetworkService> -VMSubnet <VMSubnet>
 [-IPv4Address <String>] [-IPv6Address <String>] [-Description <String>] -Name <String>
 [-ConnectionType <NetworkConnectionType>] [-NetworkAdapter <NetworkServiceAdapterInfo>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCNetworkConnection** cmdlet adds a network service connection.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -ConnectionType
Specifies a network connection type.
The acceptable values for this parameter are:

- Unknown
- FrontEnd
- BackEnd

```yaml
Type: NetworkConnectionType
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, FrontEnd, BackEnd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the network connection.

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

### -IPv4Address
Specifies an IPv4 address.

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

### -IPv6Address
Specifies an IPv6 address.

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

### -LogicalNetworkDefinition
Specifies a logical network definition (also called a network site) that contains the subnet that the IP address pool serves.
The subnet is specified by the *VMSubnet* parameter.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: AddNetworkServiceConnectionByLND
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a network object.

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

### -NetworkAdapter
Specifies a network service adapter information object.

```yaml
Type: NetworkServiceAdapterInfo
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

### -Service
Specifies a network service object.

```yaml
Type: NetworkService
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### -VMSubnet
Specifies a virtual machine subnet object.

To obtain a **VMSubnet** object, use the Get-SCVMSubnet cmdlet.

```yaml
Type: VMSubnet
Parameter Sets: AddNetworkServiceConnectionByVMSubnet
Aliases: 

Required: True
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

[Get-SCNetworkConnection](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCNetworkConnection.md)

[Get-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMSubnet.md)

[Remove-SCNetworkConnection](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCNetworkConnection.md)

[Set-SCNetworkConnection](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCNetworkConnection.md)

