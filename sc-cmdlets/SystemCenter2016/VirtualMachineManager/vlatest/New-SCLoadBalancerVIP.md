---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4F0E8E0E-0169-4731-8536-B3BD563BC36D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIP.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIP.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerVIP.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerVIP

## SYNOPSIS
Creates a load balancer VIP on a load balancer.

## SYNTAX

```
New-SCLoadBalancerVIP [-VMMServer <ServerConnection>] -Name <String> -LoadBalancer <LoadBalancer>
 -IPAddress <String> [-LoadBalancerPort <UInt16>] [-LoadBalancerVIPTemplate <LoadBalancerVIPTemplate>]
 [-IsPersistenceEnabled <Boolean>] [-LoadBalancerConnectionPersistence <LoadBalancerConnectionPersistence>]
 [-LoadBalancerHealthMonitor <LoadBalancerHealthMonitor[]>] [-LoadBalancerProtocol <LoadBalancerProtocol>]
 [-LoadBalancingMethod <LoadBalancingMethod>] [-FrontEndVMNetwork <VMNetwork>]
 [-BackEndVirtualNetworkAdapters <VirtualNetworkAdapter[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerVIP** cmdlet creates a load balancer virtual IP (VIP) on a load balancer.

## EXAMPLES

### Example 1: Create a load balancer virtual IP 
```
PS C:\> $LBProtocol = New-SCLoadBalancerProtocol -Name "HTTPS" -HTTPSCertificateSubjectName "C=US,ST=WA,L=Redmond,O=Contoso,OU=Test,CN=www.contoso.com/emailAddress=contoso@contoso.com" -HTTPSReencryptConnection $True -TerminateHTTPS $True
PS C:\> $LBConnectionPersistence = New-SCLoadBalancerConnectionPersistence -Name "SourceIP" -Value "255.255.255.0"
PS C:\> $LBHealthMonitor = New-SCLoadBalancerHealthMonitor -Name "HTTPMonitor" -Request "Get /Index.html HTTP/1.1" -Response 200 -IntervalSeconds 5 -TimeoutSeconds 2 -ProtocolName "HTTPS"
PS C:\> $LBMethod = New-SCLoadBalancingMethod -Name "LeastConnections"
PS C:\> $LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com"
PS C:\> New-SCLoadBalancerVIP -Name "LoadBalancerVIP01" -IPAddress 10.0.0.1 -LoadBalancer $LoadBalancer -LoadBalancerConnectionPersistence $LBConnectionPersistence -LoadBalancerProtocol $LBProtocol -LoadBalancingMethod $LBMethod -LoadBalancerHealthMonitor $LBHealthMonitor -LoadBalancerPort 80
```

The first command creates a load balancer protocol object and stores the object in the $LBProtocol variable.

The second command creates a load balancer connection persistence object and stores the object in the $LBConnectionPersistence variable.

The third command creates a load balancer health monitor object and stores the object in the $LBHealthMonitor variable.

The fourth command creates a load balancing method object and stores the object in the $LBMethod variable.

The fifth command gets the load balancer object with the address LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The last command creates a load balancer VIP named LoadBalancerVIP01 using the load balancer stored in $LoadBalancer and the objects created in the previous commands.

## PARAMETERS

### -BackEndVirtualNetworkAdapters
Specifies the list of **VirtualNetworkAdapter** objects of the VMs that are load balanced.

```yaml
Type: VirtualNetworkAdapter[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontEndVMNetwork
Specifies the virtual machine network for the front end IP of the load balancing rule.
This is the network from which the load balancer VIP is taken.

```yaml
Type: VMNetwork
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

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

### -IsPersistenceEnabled
Indicates whether persistence is enabled for a load balancer VIP.
When set to $True, the load balancer attempts to direct a particular client to the same virtual machine behind the load balancer.

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
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerConnectionPersistence
Specifies a load balancer connection persistence object.

```yaml
Type: LoadBalancerConnectionPersistence
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerHealthMonitor
Specifies a load balancer health monitor object.

```yaml
Type: LoadBalancerHealthMonitor[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerPort
Specifies the port to use when configuring a VIP in a load balancer.

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

### -LoadBalancerProtocol
Specifies the protocol to use when connecting to a load balancer, or a load balancer protocol object.

```yaml
Type: LoadBalancerProtocol
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerVIPTemplate
Specifies a load balancer VIP template.

```yaml
Type: LoadBalancerVIPTemplate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancingMethod
Specifies the load balancing method to use.
Valid values are: 

- RoundRobin
- LeastConnectionsmember
- Observedmember
- Predictivemember
- Ratiomember
- Fastestmember
- LeastConnections
- Observednode
- Predictivenode
- Rationode
- FastestResponseTime
- LeastSessions
- None

To determine the available methods for a specific load balancer, use the following command: `(Get-SCLoadBalancer)[0].AvailableLoadBalancingMethods`

```yaml
Type: LoadBalancingMethod
Parameter Sets: (All)
Aliases: 

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

### LoadBalancerVIP
This cmdlet returns a **LoadBalancerVIP** object.

## NOTES
* Requires a VMM load balancer object, which can be retrieved using the **Get-SCLoadBalancer** cmdlet.

## RELATED LINKS

[Get-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancer.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLoadBalancerVIP.md)

[New-SCLoadBalancerConnectionPersistence](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerConnectionPersistence.md)

[New-SCLoadBalancerHealthMonitor](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerHealthMonitor.md)

[New-SCLoadBalancerProtocol](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerProtocol.md)

[New-SCLoadBalancingMethod](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancingMethod.md)

[Read-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLoadBalancerVIP.md)

[Remove-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLoadBalancerVIP.md)

