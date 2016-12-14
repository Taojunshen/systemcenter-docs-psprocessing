---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: B7650664-31A1-4CEF-A5B4-05C5B243D6EE
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHost

## SYNOPSIS
Gets virtual machine host objects from the Virtual Machine Manager database.

## SYNTAX

### Connection (Default)
```
Get-SCVMHost [-VMMServer <ServerConnection>] [[-ComputerName] <String>] [-ID <Guid>] [<CommonParameters>]
```

### VMHostGroup
```
Get-SCVMHost -VMHostGroup <HostGroup> [[-ComputerName] <String>] [<CommonParameters>]
```

### VMHostCluster
```
Get-SCVMHost -VMHostCluster <HostCluster> [[-ComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHost** cmdlet gets one or more virtual machine host objects from the Virtual Machine Manager (VMM) database.
Virtual machine hosts are physical computers that are managed by VMM on which you can deploy virtual machines.

VMM supports the following types of hosts: 

- Hyper-V hosts
- VMware ESX hosts
- Citrix XenServer hosts

For more information about virtual machine hosts in Virtual Machine Manager, type `Get-Help Add-VMHost -Detailed`.

## EXAMPLES

### Example 1: Get all hosts managed by the specified VMM server
```
PS C:\>Get-SCVMHost -VMMServer "VMMServer01.Contoso.com"
```

This command gets all host objects for all managed by VMMServer01 and displays the host properties to the user.

### Example 2: Get a host by name
```
PS C:\>Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
```

This command gets the host object named VMHost01 in the Contoso.com domain and displays the host properties to the user.

### Example 3: Get all hosts in a specific host group and display information about them to the user
```
PS C:\>$HostGroup = Get-SCVMHostGroup -Name "HostGroup01" -VMMServer "VMMServer01.Contoso.com"
PS C:\> $HostsInHG = Get-SCVMHost -VMHostGroup $HostGroup
PS C:\> $HostsInHG | Format-Table -Property Name, VMs
```

The first command gets the host group object named HostGroup01 from VMMServer01 and stores the object in the $HostGroup variable.

The second command gets all host objects in the host group stored in $HostGroup and stores the objects in the $HostsInHG variable.

The last command uses the pipeline operator to pass all host objects stored in $HostsInHG to the Format-Table cmdlet, which displays the name of each host and the virtual machines deployed on that host in a table.

### Example 4: Get all hosts in a specific host cluster and display information about them to the user
```
PS C:\>$Cluster = Get-SCVMHostCluster -Name "Cluster01.Contoso.com" -VMMServer "VMMServer01.Contoso.com"
PS C:\> $HostsInCluster = Get-SCVMHost -VMHostCluster $Cluster
PS C:\> $HostsInCluster | Format-Table -Property Name, VirtualizationPlatform
```

The first command gets the host cluster object named Cluster01 from VMMServer01 and stores the object in the $Cluster variable.

The second command gets all host objects in Cluster01 and stores the objects in the $HostsInCluster variable.

The last command passes all host objects stored in $HostsInCluster to the Format-Table cmdlet, which displays the name and virtualization platform of each host in Cluster01.

### Example 5: Get a specific host located on a perimeter network by its IP address
```
PS C:\>$VMHost = Get-VMHost -ComputerName 10.199.53.5 -VMMServer "VMMServer01.Contoso.com"
PS C:\> $VMHost | Select-Object -Property ComputerName, OperatingSystem
```

The first command gets the host object located on a perimeter network whose IP address is 10.199.53.5 from VMMServer01 and stores the object in the $VMHost variable.

The second command uses the pipeline operator to pass the host object in $VMHost to the **Select-Object** cmdlet, which displays the computer name and operating system for the host.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

Note: See the examples for a specific cmdlet to determine how that cmdlet specifies the computer name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: Connection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostCluster
Specifies a VMM host cluster object.

```yaml
Type: HostCluster
Parameter Sets: VMHostCluster
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: VMHostGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: Connection
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

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCVMHost.md)

