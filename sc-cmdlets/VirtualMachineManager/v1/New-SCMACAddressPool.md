---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCMACAddressPool.md
schema: 2.0.0
ms.assetid: 04BC3777-7FEA-461F-B4EA-AFDEB7810A5A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCMACAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCMACAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCMACAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCMACAddressPool

## SYNOPSIS
Creates a MAC address pool.

## SYNTAX

```
New-SCMACAddressPool [-VMMServer <ServerConnection>] -Name <String> [-Description <String>]
 -MACAddressRangeStart <String> -MACAddressRangeEnd <String> -VMHostGroup <HostGroup[]> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCMACAddressPool** cmdlet creates a Media Access Control (MAC) address pool.
A MAC address pool can be associated with one or more Virtual Machine Manager (VMM) host groups.

## EXAMPLES

### Example 1: Create a MAC address pool
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> New-SCMACAddressPool -Name "MAC Address Pool 01" -VMHostGroup $HostGroup -MACAddressRangeStart "00-1D-D8-B7-1C-00" -MACAddressRangeEnd "00-1D-D8-F4-1F-FF"
```

The first command gets the host group named Production and stores it in the $HostGroup variable.

The second command creates a MAC address pool named MAC Address Pool 01 with an address range beginning with "00-1D-D8-B7-1C-00" and ending with "00-1D-D8-F4-1F-FF", as delineated by the *MACAddressRangeStart* and *MACAddressRangeEnd* parameters.
The command also associates the pool with the host group stored in $HostGroup.

## PARAMETERS

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

### -MACAddressRangeEnd
Specifies the last address in a range of static MAC addresses.

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

### -MACAddressRangeStart
Specifies the first address in a range of static MAC addresses.

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

### -Name
Specifies the name of a VMM object.

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

### -VMHostGroup
Specifies a virtual machine host group object.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* Requires a VMM host group object, which can be retrieved by using the Get-SCVMHostGroup cmdlet.

## RELATED LINKS

[Get-SCMACAddressPool](xref:VirtualMachineManager/v1/Get-SCMACAddressPool.md)

[Get-SCVMHostGroup](xref:VirtualMachineManager/v1/Get-SCVMHostGroup.md)

[Remove-SCMACAddressPool](xref:VirtualMachineManager/v1/Remove-SCMACAddressPool.md)

[Set-SCMACAddressPool](xref:VirtualMachineManager/v1/Set-SCMACAddressPool.md)

