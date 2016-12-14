---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCNetworkService.md
schema: 2.0.0
ms.assetid: 3388DEC9-A75C-4093-863A-CF4A30F6B7CA
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCNetworkService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCNetworkService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCNetworkService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCNetworkService

## SYNOPSIS
Modifies a network service.

## SYNTAX

```
Set-SCNetworkService [-ProvisionSelfSignedCertificatesForNetworkService <Boolean>]
 [-VMMServer <ServerConnection>] [-NetworkService] <NetworkService> [-Name <String>] [-Description <String>]
 [-ConnectionString <String>] [-Manufacturer <String>] [-Model <String>] [-Version <String>]
 [-RunAsAccount <RunAsAccount>] [-ConfigurationProvider <ConfigurationProvider>]
 [-BandwidthCapacityKBps <UInt64>] [-RemoveBandwidthCapacity] [-Certificate <ClientCertificate[]>]
 [-AddVMHostGroup <HostGroup[]>] [-RemoveVMHostGroup <HostGroup[]>] [-Force]
 [-AddLogicalNetworkVIP <LogicalNetwork[]>] [-RemoveLogicalNetworkVIP <LogicalNetwork[]>]
 [-AddLogicalNetworkDedicatedIP <LogicalNetwork[]>] [-RemoveLogicalNetworkDedicatedIP <LogicalNetwork[]>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCNetworkService** cmdlet modifies a network service.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -AddLogicalNetworkDedicatedIP
Specifies an array of logical network dedicated IP addresses that this cmdlet adds to an existing logical network array.

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
Specifies an array of logical network virtual IP addresses that this cmdlet adds to an existing logical network array.

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

### -BandwidthCapacityKBps
Specifies the bandwidth capacity, in kilobytes per second (KBps), of a network service.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
Specifies an array of security certificate objects.

```yaml
Type: ClientCertificate[]
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
If no configuration provider is found, the load balancer will not be added.

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

### -ConnectionString
Specifies the information required to connect to the virtual switch extension manager.

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

### -Description
Specifies a description for the network service.

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

### -Manufacturer
Specifies the name of the company that manufactured a physical device.
The acceptable values for this parameter are:



- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
- Single quote (')

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

### -NetworkService
Specifies a network service object.

```yaml
Type: NetworkService
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

### -ProvisionSelfSignedCertificatesForNetworkService


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

### -RemoveBandwidthCapacity
Removes bandwidth capacity.

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

### -RemoveLogicalNetworkDedicatedIP
Specifies an array of logical network dedicated IP addresses that this cmdlet removes.

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
Removes a logical network virtual IP address.

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
Removes one or more host groups from a host group array or private cloud.

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

### -Version
Specifies a version.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCNetworkService.md)

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCNetworkService.md)

[Read-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCNetworkService.md)

[Remove-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCNetworkService.md)

[Test-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Test-SCNetworkService.md)

