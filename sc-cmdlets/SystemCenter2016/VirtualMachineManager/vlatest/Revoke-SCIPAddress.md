---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCIPAddress.md
schema: 2.0.0
ms.assetid: 89AE7650-0D57-4445-BD5B-EFA9CC44E40F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCIPAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCIPAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCIPAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Revoke-SCIPAddress

## SYNOPSIS
Returns an allocated IP address to the static IP address pool.

## SYNTAX

```
Revoke-SCIPAddress [-VMMServer <ServerConnection>] [-AllocatedIPAddress] <AllocatedIPAddress>
 [-ReturnToPool <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Revoke-SCIPAddress** cmdlet returns an allocated IP address to the static IP address pool.

For information about allocating IP addresses, type `Get-Help Grant-SCIPAddress -Detailed`.

## EXAMPLES

### Example 1: Return an unassigned allocated IP address to the IP address pool
```
PS C:\>$IPAddressPool = Get-SCStaticIPAddressPool -IPv4 -Subnet "10.0.0.0/24"
PS C:\> $IPAddress = Get-SCIPAddress -StaticIPAddressPool $IPAddressPool -Unassigned
PS C:\> Revoke-SCIPAddress -AllocatedIPAddress $IPAddress[0]
```

The first command gets the static IP address pool object with the IPv4 subnet of 10.0.0.0/24 and stores the object in the $IPAddressPool variable.

The second command gets all unassigned allocated IP address objects for the static IP address pool stored in $IPAddressPool and stores the objects in the $IPAddress variable.

The last command revokes the first IP address stored in $IPAddress and returns the address to the IP address pool.

## PARAMETERS

### -AllocatedIPAddress
Specifies an IP address that has been allocated from an IP address pool.

```yaml
Type: AllocatedIPAddress
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### CloudDRPairingInfoData
This cmdlet returns a **CloudDRPairingInfoData** object.

## NOTES

## RELATED LINKS

[Get-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCIPAddress.md)

[Get-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStaticIPAddressPool.md)

[Grant-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCIPAddress.md)

[Set-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCIPAddress.md)

