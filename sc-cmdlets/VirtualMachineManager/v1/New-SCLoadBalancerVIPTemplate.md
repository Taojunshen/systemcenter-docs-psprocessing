---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCLoadBalancerVIPTemplate.md
schema: 2.0.0
ms.assetid: 411A1995-B947-49F0-84E7-6FB846A981DD
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerVIPTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerVIPTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerVIPTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerVIPTemplate

## SYNOPSIS
Creates a load balancer VIP template used to create a load balancer VIP.

## SYNTAX

### Generic (Default)
```
New-SCLoadBalancerVIPTemplate [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 [-LoadBalancerConnectionPersistence <LoadBalancerConnectionPersistence>]
 [-LoadBalancerHealthMonitor <LoadBalancerHealthMonitor[]>] -LoadBalancerProtocol <LoadBalancerProtocol>
 -LoadBalancerPort <UInt16> [-LoadBalancerBackEndPort <UInt16>] -LoadBalancingMethod <LoadBalancingMethod>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Specific
```
New-SCLoadBalancerVIPTemplate [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -LoadBalancerManufacturer <String> -LoadBalancerModel <String>
 [-LoadBalancerConnectionPersistence <LoadBalancerConnectionPersistence>]
 [-LoadBalancerHealthMonitor <LoadBalancerHealthMonitor[]>] -LoadBalancerProtocol <LoadBalancerProtocol>
 -LoadBalancerPort <UInt16> [-LoadBalancerBackEndPort <UInt16>] -LoadBalancingMethod <LoadBalancingMethod>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerVIPTemplate** cmdlet creates a load balancer virtual IP (VIP) template used to create a load balancer VIP.

For information about creating a load balancer VIP, type `Get-Help New-SCLoadBalancerVIP -Detailed`.

## EXAMPLES

### Example 1: Create a specific load balancer virtual IP (VIP) template
```
PS C:\>$LBProtocol = New-SCLoadBalancerProtocol -Name "HTTPS" -HTTPSCertificate "C=US,ST=WA,L=Redmond,O=Contoso,OU=Test,CN=www.contoso.com/emailAddress=contoso@contoso.com" -HTTPSReencryptconnection $True -TerminateHTTPS $True
PS C:\> $LBConnectionPersistence = New-SCLoadBalancerConnectionPersistence -Name "Source IP" -Value "255.255.255.0"
PS C:\> $LBHealthMonitor = New-SCLoadBalancerHealthMonitor -Name "HTTPMonitor" -ProtocolName "HTTP" -Request "Get /Index.html HTTP/1.1" -Response 200 -IntervalSeconds 15 -TimeoutSeconds 20
PS C:\> $LBMethod = New-SCLoadBalancingMethod -Name "Least Connections"
PS C:\> New-SCLoadBalancerVIPTemplate -Name "VIPTemplate01" -Description "Specific virtual IP Template" -LoadBalancerManufacturer "LB Manufacturer" -LoadBalancerModel "LB01" -LoadBalancerPort "123" -LoadBalancerConnectionPersistence $LBConnectionPersistence -LoadBalancerProtocol $LBProtocol -LoadBalancingMethod $LBMethod  -LoadBalancerHealthMonitor $LBHealthMonitor
```

The first command creates a load balancer protocol object specifying that the HTTPS connection terminates at the load balancer, and then the connection is re-encrypted with the server.
The command then stores the object in the $LBProtocol variable.

The second command creates a load balancer connection presistence object with a value of 255.255.255.0, and then stores the object in the $LBConnectionPersistence variable.

The third command creates a load balancer health monitor object specifying the load balancer protocol, the response, the interval in seconds, and the timeout in seconds.
The command then stores the object in the $LBHealthMonitor variable.

The fourth command creates a load balancer method object with the value of LeastConnections and stores the object in the $LBMethod variable.

The last command creates a load balancer VIP template named VIPTemplate01 that is specific to the load balancer model LB01 manufactured by LB Manufacturer using the values for the objects stored in the $LBConnectionPersistence, $LBProtocol, $LBMethod, and $LBHealthMonitor created in the previous commands.

## PARAMETERS

### -Description
Specifies a description for the VIP template.

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

### -LoadBalancerBackEndPort
Specifies the port on which the backend service is running which is being load balanced.

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

### -LoadBalancerManufacturer
Specifies the name of the company that manufactured a load balancer.
The acceptable values for this parameter are:


- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
- Single quote (')

```yaml
Type: String
Parameter Sets: Specific
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerModel
Specifies the model of a load balancer

```yaml
Type: String
Parameter Sets: Specific
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerPort
Specifies the port to use when configuring a virtual IP (VIP) in a load balancer.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancingMethod
Specifies the load balancing method to use.
The acceptable values for this parameter are:

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

To determine the available methods for a specific load balancer, use this command: `(Get-SCLoadBalancer)\[0\].AvailableLoadBalancingMethods`

```yaml
Type: LoadBalancingMethod
Parameter Sets: (All)
Aliases: 

Required: True
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

## NOTES

## RELATED LINKS

[Get-SCLoadBalancerVIPTemplate](xref:VirtualMachineManager/v1/Get-SCLoadBalancerVIPTemplate.md)

[New-SCLoadBalancerConnectionPersistence](xref:VirtualMachineManager/v1/New-SCLoadBalancerConnectionPersistence.md)

[New-SCLoadBalancerHealthMonitor](xref:VirtualMachineManager/v1/New-SCLoadBalancerHealthMonitor.md)

[New-SCLoadBalancerProtocol](xref:VirtualMachineManager/v1/New-SCLoadBalancerProtocol.md)

[New-SCLoadBalancingMethod](xref:VirtualMachineManager/v1/New-SCLoadBalancingMethod.md)

[Remove-SCLoadBalancerVIPTemplate](xref:VirtualMachineManager/v1/Remove-SCLoadBalancerVIPTemplate.md)

[Set-SCLoadBalancerVIPTemplate](xref:VirtualMachineManager/v1/Set-SCLoadBalancerVIPTemplate.md)

