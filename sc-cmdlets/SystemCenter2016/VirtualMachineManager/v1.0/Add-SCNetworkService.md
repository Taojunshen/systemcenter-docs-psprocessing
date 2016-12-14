---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCNetworkService.md
schema: 2.0.0
ms.assetid: C83BA476-4B47-4003-B630-2B96A6853082
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCNetworkService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCNetworkService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Add-SCNetworkService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCNetworkService

## SYNOPSIS
Adds a network service to VMM.

## SYNTAX

### ByModel (Default)
```
Add-SCNetworkService [-ProvisionSelfSignedCertificatesForNetworkService <Boolean>]
 [-VMMServer <ServerConnection>] [-ConnectionString] <String> -Manufacturer <String> -Model <String>
 [-Version <String>] -RunAsAccount <RunAsAccount> -VMHostGroup <HostGroup[]> -Name <String>
 [-Description <String>] [-BandwidthCapacityKBps <UInt64>] [-Certificate <ClientCertificate[]>]
 [-LogicalNetworkVIP <LogicalNetwork[]>] [-LogicalNetworkDedicatedIP <LogicalNetwork[]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ByProvider
```
Add-SCNetworkService [-ProvisionSelfSignedCertificatesForNetworkService <Boolean>]
 [-VMMServer <ServerConnection>] [-ConnectionString] <String> [-Version <String>] -RunAsAccount <RunAsAccount>
 -VMHostGroup <HostGroup[]> -Name <String> [-Description <String>]
 -ConfigurationProvider <ConfigurationProvider> [-BandwidthCapacityKBps <UInt64>]
 [-Certificate <ClientCertificate[]>] [-LogicalNetworkVIP <LogicalNetwork[]>]
 [-LogicalNetworkDedicatedIP <LogicalNetwork[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCNetworkService** cmdlet adds a network service to Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Add a network service for a network controller to VMM
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -ID "dc90a558-c402-4a70-9f6b-e50bc2fad540"
PS C:\> $ConfigurationProvider = Get-SCConfigurationProvider -Name "Microsoft Network Controller"
PS C:\> $VmHostGroup = @()
PS C:\> $VmHostGroup += Get-SCVMHostGroup -Name "All Hosts"
PS C:\> $Certificates = @()
PS C:\> $Certificates += Get-SCCertificate -ComputerName "networkcontroller.contoso.com" -TCPPort 443
PS C:\> Add-SCNetworkService -Name "NetworkController" -RunAsAccount $runAsAccount -ConfigurationProvider $ConfigurationProvider -VMHostGroup $vmHostGroup -ConnectionString "serverUrl=https://networkcontroller.contoso.com;serviceName=NC_Service" -Certificate $Certificates -ProvisionSelfSignedCertificatesForNetworkService $True
```

The first command gets the run as account that is used by VMM to communicate with network service.
The command stores it in the $RunAsAccount variable.

The second command gets the configuration provider for network controller.

The third command creates an array variable named $VmHostGroup.
The fourth command adds a host group to which the network service is accessible to $VmHostGroup.

The fifth command creates an array variable named $Certificates.
The sixth command adds the certificated available for the network controller to $Certificates.

The final command adds network service for a network controller to VMM.
The command specifies the values created in previous commands.
Because this example uses self-signed certificates for the network controller, the *ProvisionSelfSignedCertificatesForNetworkService* has a value of $True.

## PARAMETERS

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
If no configuration provider is found, the load balancer is not added.

```yaml
Type: ConfigurationProvider
Parameter Sets: ByProvider
Aliases: 

Required: True
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

Required: True
Position: 0
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

### -LogicalNetworkDedicatedIP
Specifies an array of logical network objects.

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
Specifies an array of logical network objects.

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
The acceptable values for this parameter are:



- Letters (a-z) 
- Numbers (0-9) 
- Underscore (_)
- Hyphen (-)
- Dot (.)
- Single quote (')

```yaml
Type: String
Parameter Sets: ByModel
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
Parameter Sets: ByModel
Aliases: 

Required: True
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
Specifies a virtual machine host group object or an array of host group objects.

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

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCNetworkService.md)

[Read-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1.0/Read-SCNetworkService.md)

[Remove-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCNetworkService.md)

[Set-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCNetworkService.md)

[Test-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1.0/Test-SCNetworkService.md)

