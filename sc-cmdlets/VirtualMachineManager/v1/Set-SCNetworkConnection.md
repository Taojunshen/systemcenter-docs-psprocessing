---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkConnection.md
schema: 2.0.0
ms.assetid: D87E4154-BE0C-4527-BBDD-5C0164DC5C52
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNetworkConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNetworkConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNetworkConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCNetworkConnection

## SYNOPSIS
Modifies a network service connection.

## SYNTAX

### SetNetworkServiceConnectionByLND
```
Set-SCNetworkConnection [-VMMServer <ServerConnection>] [-NetworkServiceConnection] <NetworkServiceConnection>
 [-LogicalNetworkDefinition <LogicalNetworkDefinition>] [-IPv4Address <String>] [-IPv6Address <String>]
 [-Description <String>] [-Name <String>] [-NetworkAdapter <NetworkServiceAdapterInfo>] [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SetNetworkServiceConnectionByVMSubnet
```
Set-SCNetworkConnection [-VMMServer <ServerConnection>] [-NetworkServiceConnection] <NetworkServiceConnection>
 [-VMSubnet <VMSubnet>] [-IPv4Address <String>] [-IPv6Address <String>] [-Description <String>]
 [-Name <String>] [-NetworkAdapter <NetworkServiceAdapterInfo>] [-Force] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCNetworkConnection** cmdlet modifies a network service connection.

## EXAMPLES

### 1:
```

```

## PARAMETERS

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -LogicalNetworkDefinition
Specifies a logical network definition (also called a network site) that contains the subnet that the IP address pool serves as specified by the *Subnet* parameter.

```yaml
Type: LogicalNetworkDefinition
Parameter Sets: SetNetworkServiceConnectionByLND
Aliases: 

Required: False
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

Required: False
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

### -NetworkServiceConnection
Specifies a network service connection object.

```yaml
Type: NetworkServiceConnection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Parameter Sets: SetNetworkServiceConnectionByVMSubnet
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

[Add-SCNetworkConnection](xref:VirtualMachineManager/v1/Add-SCNetworkConnection.md)

[Get-SCNetworkConnection](xref:VirtualMachineManager/v1/Get-SCNetworkConnection.md)

[Get-SCVMSubnet](xref:VirtualMachineManager/v1/Get-SCVMSubnet.md)

[Remove-SCNetworkConnection](xref:VirtualMachineManager/v1/Remove-SCNetworkConnection.md)

