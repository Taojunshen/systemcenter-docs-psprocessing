---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLogicalNetworkDefinition.md
schema: 2.0.0
ms.assetid: AC0A631A-B45B-4FAE-ADB8-5F59E7C7EC46
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCNativeUplinkPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCNativeUplinkPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCNativeUplinkPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCNativeUplinkPortProfile

## SYNOPSIS
Creates a native uplink port profile.

## SYNTAX

```
New-SCNativeUplinkPortProfile [-LogicalNetworkDefinition <LogicalNetworkDefinition[]>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>]
 [-EnableNetworkVirtualization <Boolean>]
 [-LBFOLoadBalancingAlgorithm <NetworkAdapterLBFOLoadBalancingAlgorithm>]
 [-LBFOTeamMode <NetworkAdapterLBFOTeamMode>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCNativeUplinkPortProfile** cmdlet creates an object for a native uplink port profile.

## EXAMPLES

### Example 1: Create a native uplink port profile by using a logical network definition
```
PS C:\>$LogNetDefinition = Get-SCLogicalNetworkDefinition -Name "Logical Network Definition 01"
PS C:\> New-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01" -LogicalNetworkDefinition $LogNetDefinition -EnableNetworkVirtualization $True
```

The first command gets the logical network definition object named Logical Network Definition 01 and stores the object in the $LogNetDefinition variable.

The second command creates a native uplink port profile named NativeUplinkPortProfile01 by using the network definition object named Logical Network Definition 01, and enables network virtualization.

## PARAMETERS

### -Description
Specifies a description for the port profile.

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

### -EnableNetworkVirtualization
Indicates whether network virtualization is enabled.
The default value is $False.

```yaml
Type: Boolean
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

### -LBFOLoadBalancingAlgorithm
Specifies a load balancing algorithm for a load balancing and failover (LBFO) network adapter.
The acceptable values for this parameter are:

- TransortPorts
- IPAddresses
- MACAddresses
- HyperVPort
- Dynamic
- HostDefault

```yaml
Type: NetworkAdapterLBFOLoadBalancingAlgorithm
Parameter Sets: (All)
Aliases: 
Accepted values: TransportPorts, IPAddresses, MacAddresses, HyperVPort, Dynamic, HostDefault

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LBFOTeamMode
Specifies a team mode for a load balancing and failover (LBFO) network adapter.

```yaml
Type: NetworkAdapterLBFOTeamMode
Parameter Sets: (All)
Aliases: 
Accepted values: Static, SwitchIndependent, Lacp

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetworkDefinition
Specifies a logical network definition (also called a network site) that contains the subnet that the IP address pool serves.
The subnet is specified by the *Subnet* parameter.

```yaml
Type: LogicalNetworkDefinition[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCLogicalNetworkDefinition](xref:VirtualMachineManager/v1/Get-SCLogicalNetworkDefinition.md)

[Get-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md)

[Remove-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Remove-SCNativeUplinkPortProfile.md)

[Set-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Set-SCNativeUplinkPortProfile.md)

