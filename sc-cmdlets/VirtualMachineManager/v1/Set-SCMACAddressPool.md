---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCMACAddressPool.md
schema: 2.0.0
ms.assetid: CEB264CF-0D0B-4B72-86B7-3A0BB870C3F0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCMACAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCMACAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCMACAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCMACAddressPool

## SYNOPSIS
Modifies a MAC address pool.

## SYNTAX

```
Set-SCMACAddressPool [-VMMServer <ServerConnection>] [-MACAddressPool] <MACAddressPool> [-Name <String>]
 [-Description <String>] [-MACAddressRangeStart <String>] [-MACAddressRangeEnd <String>]
 [-AddVMHostGroup <HostGroup[]>] [-RemoveVMHostGroup <HostGroup[]>]
 [-SupportedVirtualizationPlatforms <VirtualizationPlatform[]>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCMACAddressPool** cmdlet modifies a Virtual Machine Manager (VMM) Media Access Control (MAC) address pool.
For example, you can add a host group to or remove a host group from a MAC address pool.
A MAC address pool can be associated with one or more host groups.

## EXAMPLES

### Example 1: Change the host groups associated with a MAC address pool
```
PS C:\>$MACPool = Get-SCMACAddressPool -Name "MAC Address Pool 01" 
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup03\Production" }
PS C:\> Set-SCMacAddressPool -MACAddressPool $MACPool -AddVMHostGroup $HostGroup
```

The first command gets the MAC address pool object named MAC Address Pool 01 and stores the object in the $MACPool variable.

The second command gets the host group object named All Hosts\HostGroup03\Production and stores the object the $HostGroup variable.

The last command updates adds the host group stored in $HostGroup to the MAC address pool stored in $MACPool.
In this case, MAC Address Pool 01 is now also associated with the host group named All Hosts\HostGroup03\Production in addition to the host groups it was previously associated with.

## PARAMETERS

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

### -Description
Specifies a description for the address pool.

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

### -MACAddressPool
Specifies a MAC address pool.

```yaml
Type: MACAddressPool
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MACAddressRangeEnd
Specifies the last address in a range of static MAC addresses.

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

### -MACAddressRangeStart
Specifies the first address in a range of static MAC addresses.

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
Specifies the name of a VMM object.

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

### -SupportedVirtualizationPlatforms
Specifies one or more virtualization platform objects.

```yaml
Type: VirtualizationPlatform[]
Parameter Sets: (All)
Aliases: 
Accepted values: Unknown, VirtualServer, HyperV, VMWareVC, VMWareESX, XENServer

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

### MACAddressPool
This cmdlet returns a **MACAddressPool** object.

## NOTES

## RELATED LINKS

[Get-SCMACAddressPool](xref:VirtualMachineManager/v1/Get-SCMACAddressPool.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[New-SCMACAddressPool](xref:VirtualMachineManager/v1/New-SCMACAddressPool.md)

[Remove-SCMACAddressPool](xref:VirtualMachineManager/v1/Remove-SCMACAddressPool.md)
