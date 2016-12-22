---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C002F7D7-B0BD-4FF7-885B-844AEE03D4E5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLoadBalancer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLoadBalancer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLoadBalancer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCLoadBalancer

## SYNOPSIS
Adds a load balancer to VMM.

## SYNTAX

```
Add-SCLoadBalancer [-VMMServer <ServerConnection>] [-LoadBalancerAddress] <String> [-Port <UInt16>]
 -Manufacturer <String> -Model <String> -RunAsAccount <RunAsAccount>
 [-ConfigurationProvider <ConfigurationProvider>] -VMHostGroup <HostGroup[]>
 [-LogicalNetworkVIP <LogicalNetwork[]>] [-LogicalNetworkDedicatedIP <LogicalNetwork[]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCLoadBalancer** cmdlet adds a load balancer to Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Add a load balancer
```
PS C:\> $LBProvider = Get-SCConfigurationProvider | Where-Object { $_.Type -Eq "LoadBalancer" -And $_.Manufacturer -Eq "LBManufacturer" -And $_.Model -Eq "LB01"} 
PS C:\> $HostGroup =@()
PS C:\> $HostGroup += Get-SCVMHostGroup | Where-Object { $_.Path -Eq "All Hosts\HostGroup01" }
PS C:\> $HostGroup += Get-SCVMHostGroup | Where-Object { $_.Path -Eq "All Hosts\HostGroup02\Production" }
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "LBRunAsAcct" 
PS C:\> Add-SCLoadBalancer -ConfigurationProvider $LBProvider -VMHostGroup $HostGroup -RunAsAccount $RunAsAcct -LoadBalancerAddress "LB.Contoso.com" -Manufacturer "LBManufacturer" -Model "LB01" -Port "123"
```

The first command gets the load balancer provider object with the specified manufacturer and model and stores the object in the $LBProvider variable.

The second command creates an array named $HostGroup.
The third and fourth commands populate the $HostGroup array with host groups named HostGroup01 and Production.

The fifth command gets the Run As account object named LBRunAsAcct and stores the object in the $RunAsAcct variable.

The last command adds the load balancer using the specified Run As account.

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

### -LoadBalancerAddress
Specifies the fully qualified domain name (FQDN) or IP address of a load balancer.
Usual formats are FQDN, IPv4 or IPv6 addresses, but check with the load balancer manufacturer for the valid format for your load balancer.

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

### -LogicalNetworkDedicatedIP
Specifies the logical networks from which the back-end IP address for the load balancer should be assigned (the back-end logical network affinity).

```yaml
Type: LogicalNetwork[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetworkVIP
Specifies the logical networks from which the front-end IP address for the load balancer should be assigned (the front-end logical network affinity).

```yaml
Type: LogicalNetwork[]
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
Valid characters include: 

- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen(-)
- Dot (.)
- Single quote (')

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

### -Model
Specifies the model of a physical device.

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

### -Port
Specifies the network port to use when adding an object or creating a connection.
Valid values are: 1 to 4095.

```yaml
Type: UInt16
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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup[]
Parameter Sets: (All)
Aliases: 

Required: True
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

### LoadBalancer
This cmdlet returns a **LoadBalancer** object.

## NOTES

## RELATED LINKS

[Get-SCConfigurationProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCConfigurationProvider.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Read-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLoadBalancer.md)

[Remove-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancer.md)

[Set-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md)

[Test-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md)

