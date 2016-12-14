---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCMACAddressPool.md
schema: 2.0.0
ms.assetid: 2F4B074F-005D-4174-9FBA-E886FB15FE71
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCMACAddressPool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCMACAddressPool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCMACAddressPool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCMACAddressPool

## SYNOPSIS
Deletes a MAC address pool.

## SYNTAX

```
Remove-SCMACAddressPool [-VMMServer <ServerConnection>] [-MACAddressPool] <MACAddressPool> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCMACAddressPool** cmdlet deletes a Virtual Machine Manager (VMM) MAC (Media Access Control) address pool.

## EXAMPLES

### Example 1: Delete a MAC address pool
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $MACPool = Get-SCMACAddressPool -VMHostGroup $HostGroup -Name "MAC Address Pool 01"
PS C:\> Remove-SCMACAddressPool -MACAddressPool $MACPool
```

The first command gets the host group named "All Hosts\HostGroup02\Production" and stores it in the $HostGroup variable.

The second command gets the MAC address pool named "MAC Address Pool 01" that is associated with the host group stored in the $HostGroup variable (including its parent host group if inheritance is enabled) and stores it in the $MACPool variable.

The third command deletes the MAC address pool stored in the $MACPool variable.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### MACAddressPool
This cmdlet returns a **MACAddressPool** object.

## NOTES
* This cmdlet requires a VMM MAC address pool object, which can be retrieved by using the Get-SCMACAddressPool cmdlet.

## RELATED LINKS

[Get-SCMACAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCMACAddressPool.md)

[New-SCMACAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCMACAddressPool.md)

[Set-SCMACAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCMACAddressPool.md)

