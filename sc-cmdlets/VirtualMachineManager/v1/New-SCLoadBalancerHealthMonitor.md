---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 38c265f6-ffcf-4bbb-a25d-e49307f1f92e
schema: 2.0.0
ms.assetid: 7C9C5430-84A9-4B1E-8FCC-312068515DF0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerHealthMonitor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerHealthMonitor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerHealthMonitor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerHealthMonitor

## SYNOPSIS
Creates a load balancer health monitor object that is used when you create a load balancer virtual IP.

## SYNTAX

```
New-SCLoadBalancerHealthMonitor [-Name <String>] -ProtocolName <String> [-Request <String>]
 [-Response <String>] -IntervalSeconds <Int32> -TimeoutSeconds <Int32> [-NumberOfRetries <Int32>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerHealthMonitor** cmdlet creates a load balancer health monitor object that is used when you create a load balancer virtual IP.

For information about creating a load balancer virtual IP, type `Get-Help New-SCLoadBalancerVIP -Detailed`.

## EXAMPLES

### Example 1: Create a load balancer health monitor
```
PS C:\>$LBHealthMonitor = New-SCLoadBalancerHealthMonitor -Name "HTTPMonitor" -ProtocolName "HTTP" -Request "GET /Index.html HTTP/1.1" -Response 200 -IntervalSeconds 15 -TimeoutSeconds 20
```

This command creates a load balancer health monitor object named HTTPMonitor and stores the object in the $LBHealthMonitor variable.

## PARAMETERS

### -IntervalSeconds
Specifies the amount of time, in seconds, that a health monitor waits between sending recurring requests to a load balancer to verify that the load balancer is available.
The interval value should be larger than the timeout value.

```yaml
Type: Int32
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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfRetries
Specifies the number of times that a load balancer health monitor retries sending a request before marking the VIP member as down.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtocolName
Specifies the protocol used to communicate with a load balancer.

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

### -Request
Specifies the request that a health monitor sends to a load balancer.
Typically, this command makes an HTTP GET request for the home page of the load balancer and checks for a header response such as 200 OK.

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

### -Response
Specifies the expected response to a request that a health monitor sends to a load balancer.

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

### -TimeoutSeconds
Specifies the amount of time, in seconds, that a process waits before timing out.

```yaml
Type: Int32
Parameter Sets: (All)
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

### LoadBalancerHealthMonitor
This cmdlet returns a **LoadBalancerHealthMonitor** object.

## NOTES

## RELATED LINKS

