---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0CE3CD62-11F1-460F-90C1-5540D56AC97C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCMACAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCMACAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCMACAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Revoke-SCMACAddress

## SYNOPSIS
Returns an allocated MAC address to the MAC address pool.

## SYNTAX

```
Revoke-SCMACAddress [-VMMServer <ServerConnection>] [-AllocatedMACAddress] <AllocatedMACAddress>
 [-ReturnToPool <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-SCMACAddress** cmdlet returns an allocated MAC (Media Access Control) address to the MAC address pool.

For information about granting MAC addresses, type: `Get-Help Grant-SCMACAddress -Detailed`.

## EXAMPLES

### Example 1: Return an allocated MAC address to the MAC address pool
```
PS C:\> $HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $MACAddressPool = Get-SCMACAddressPool -VMHostGroup $HostGroup
PS C:\> $MACAddress = Get-SCMACAddress -MACAddressPool $MACAddressPool[0]
PS C:\> Revoke-SCMACAddress $MACAddress[0]
```

The first command gets the host group object at path "All Hosts\HostGroup02\Production" and stores the object in the $HostGroup variable.

The second commmand gets the MAC address pools for the host group stored in $HostGroup and stores the objects in the $MACAddressPool array.

The third command gets the allocated MAC addresses from the first MAC address pool stored in $MACAddressPool and stores the objects in $MACAddress.

The last command revokes the first MAC address stored in $MACAddress.

## PARAMETERS

### -AllocatedMACAddress
Specifies a MAC address that has been allocated from a MAC address pool.

```yaml
Type: AllocatedMACAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -ReturnToPool
Indicates whether an IP address or MAC address is returned to its address pool.
By default, this value is set to $True.

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
Specifies a Virtual Machine Manager (VMM) server object.

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

### CloudPairing[]
This cmdlet returns an array of **CloudPairing** objects.

## NOTES

## RELATED LINKS

[Get-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddress.md)

[Get-SCMACAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCMACAddressPool.md)

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Grant-SCMACAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCMACAddress.md)

