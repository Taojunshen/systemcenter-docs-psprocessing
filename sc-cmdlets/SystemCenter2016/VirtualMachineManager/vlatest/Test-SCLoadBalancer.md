---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7CCA6DD7-5415-40AA-9605-BD96AA1502F1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCLoadBalancer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCLoadBalancer

## SYNOPSIS
Tests a load balancer.

## SYNTAX

```
Test-SCLoadBalancer [-VMMServer <ServerConnection>] [-LoadBalancerAddress] <String> -Port <UInt16>
 -ConfigurationProvider <ConfigurationProvider> -RunAsAccount <RunAsAccount> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCLoadBalancer** cmdlet runs tests against a load balancer and returns the results.

## EXAMPLES

### Example 1: Test a specified load balancer
```
PS C:\> $ConfigProvider = Get-SCConfigurationProvider | where { $_.Type -eq "LoadBalancer" -and $_.Manufacturer -eq "LBManufacturer" -and $_.Model -eq "LB01"}
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "LBRunAsAcct"
PS C:\> Test-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com" -Port 123 -ConfigurationProvider $ConfigProvider -RunAsAccount $RunAsAccount
```

The first command gets the configuration provider object for the manufacturer LBManufacturer and model LB01, and stores the object in the $ConfigProvider variable.

The second command gets the Run As account named LBRunAsAccount and stores the object in the $RunAsAccount variable.

The last command tests the load balancer with the address LB01.Contoso.com, using providing the Run As account stored in $RunAsAccount as credentials to run the tests.
The command then displays the results to the user.

## PARAMETERS

### -ConfigurationProvider
Specifies a configuration provider object.
A configuration provider is a plug-in to Virtual Machine Manager (VMM) that translates VMM PowerShell commands to API calls that are specific to a type of load balancer.
If no configuration provider is specified, VMM uses the Manufacturer and Model information to choose an available configuration provider.
If no configuration provider is found, the load balancer is not added.

```yaml
Type: ConfigurationProvider
Parameter Sets: (All)
Aliases: 

Required: True
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

### -Port
Specifies the network port to use when adding an object or creating a connection.
Valid values are: 1 to 4095.

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

[Set-SCLoadBalancer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLoadBalancer.md)

