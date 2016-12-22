---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F331DBBB-6200-4D4D-BBBB-797C3C6A72E3
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLoadBalancer

## SYNOPSIS
Modifies the properties of a load balancer.

## SYNTAX

```
Set-SCLoadBalancer [-VMMServer <ServerConnection>] [-LoadBalancer] <LoadBalancer>
 [-LoadBalancerAddress <String>] [-Port <UInt16>] [-Manufacturer <String>] [-Model <String>]
 [-RunAsAccount <RunAsAccount>] [-ConfigurationProvider <ConfigurationProvider>]
 [-AddVMHostGroup <HostGroup[]>] [-RemoveVMHostGroup <HostGroup[]>] [-AddLogicalNetworkVIP <LogicalNetwork[]>]
 [-RemoveLogicalNetworkVIP <LogicalNetwork[]>] [-AddLogicalNetworkDedicatedIP <LogicalNetwork[]>]
 [-RemoveLogicalNetworkDedicatedIP <LogicalNetwork[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLoadBalancer** cmdlet modifies the properties of a load balancer.

## EXAMPLES

### Example 1: Change the configuration provider for a load balancer
```
PS C:\> $LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> $NewProvider = Get-SCConfigurationProvider | where { $_.Type -eq "LoadBalancer" -and $_.Manufacturer -eq "LB Manufacturer 2" -and $_.Model -eq "LB02"} 
PS C:\> Set-SCLoadBalancer -LoadBalancer $LoadBalancer -ConfigurationProvider $NewProvider -Manufacturer "LB Manufacturer 2" -Model "LB02"
```

The first command gets the load balancer object with the address of LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command gets the configuration provider with the Manufacturer of LB Manufacturer 2 and the model of LB02.

The third command updates the configuration provider for the load balancer stored in $LoadBalancer to the configuration provider stored in $NewProvider.

## PARAMETERS

### -AddLogicalNetworkDedicatedIP
Specifies the logical network from which this cmdlet assigns an IP address to a virtual machine in a service tier as the back-end address for a service.

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

### -AddLogicalNetworkVIP
Specifies the logical network from which this cmdlet assigns a virtual IP (VIP) address to a load balancer VIP as the front-end address for a service.

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

### -LoadBalancer
Specifies a load balancer object.

```yaml
Type: LoadBalancer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancerAddress
Specifies the fully qualified domain name (FQDN) or IP address of a load balancer.
Usual formats are FQDN, IPv4 or IPv6 addresses, but check with the load balancer manufacturer for the valid format for your load balancer.

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
Valid characters include:

- 

Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
-  Single quote (')

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

### -RemoveLogicalNetworkDedicatedIP
Specifies the logical network from which an IP address was assigned to a virtual machine in a service tier as the front-end address for a service, and is now removed.

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

### -RemoveLogicalNetworkVIP
Specifies the logical network from which a virtual IP (VIP) address was assigned to a load balancer as the front-end address for a service, and is now removed.

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

### -RemoveVMHostGroup
Specifies an array of host groups that this cmdlet removes from a host group array or private cloud.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancer
This cmdlet returns a **LoadBalancer** object.

## NOTES

## RELATED LINKS

[Add-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLoadBalancer.md)

[Get-SCConfigurationProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCConfigurationProvider.md)

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Read-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLoadBalancer.md)

[Remove-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancer.md)

[Test-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md)

