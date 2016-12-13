---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCNativeUplinkPortProfile.md
schema: 2.0.0
ms.assetid: D3C113F4-6C0E-41EF-B8B0-178D65DF3E66
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNativeUplinkPortProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNativeUplinkPortProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCNativeUplinkPortProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCNativeUplinkPortProfile

## SYNOPSIS
Updates a native uplink port profile.

## SYNTAX

```
Set-SCNativeUplinkPortProfile [-AddLogicalNetworkDefinition <LogicalNetworkDefinition[]>]
 [-RemoveLogicalNetworkDefinition <LogicalNetworkDefinition[]>] [-VMMServer <ServerConnection>]
 [-NativeUplinkPortProfile] <NativeUplinkPortProfile> [-Name <String>] [-Description <String>]
 [-EnableNetworkVirtualization <Boolean>]
 [-LBFOLoadBalancingAlgorithm <NetworkAdapterLBFOLoadBalancingAlgorithm>]
 [-LBFOTeamMode <NetworkAdapterLBFOTeamMode>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCNativeUplinkPortProfile** cmdlet updates a native uplink port profile.
You can use it to add or remove a logical network definition.

## EXAMPLES

### Example 1: Remove a logical network definition from a native uplink port profile
```
PS C:\>$LogNetDefinition = Get-SCLogicalNetworkDefinition -Name "Logical Network Definition 01" 
PS C:\> Get-SCNativeUplinkPortProfile -Name "NativeUplinkPortProfile01" | Set-SCNativeUplinkPortProfile -RemoveLogicalNetworkDefinition $LogNetDefinition
```

The first command gets the logical network definition object named Logical Network Definition 01 and stores the object in the $LogNetDefinition variable.

The second command gets the native uplink port profile object named NativeUplinkPortProfile01 and uses the pipeline operator to pass the object to **Set-SCNativeUplinikPortProfile**.
This removes Logical Network Definition 01 from NativeUplinkPortProfile01.

## PARAMETERS

### -AddLogicalNetworkDefinition
Specifies an array of logical network definition objects that this cmdlet adds.

To get a logical network definition object, use the Get-SCLogicalNetworkDefinition cmdlet.

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
Specifies a load balancing and failover (LBFO) network adapter load balancing algorithm.
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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -NativeUplinkPortProfile
Specifies a native uplink port profile object.

```yaml
Type: NativeUplinkPortProfile
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

### -RemoveLogicalNetworkDefinition
Specifies an array of logical network definition objects to remove.

To get a logical network definition object, use the Get-SCLogicalNetworkDefinition cmdlet.

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

[Get-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Get-SCNativeUplinkPortProfile.md)

[New-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/New-SCNativeUplinkPortProfile.md)

[Remove-SCNativeUplinkPortProfile](xref:VirtualMachineManager/v1/Remove-SCNativeUplinkPortProfile.md)

