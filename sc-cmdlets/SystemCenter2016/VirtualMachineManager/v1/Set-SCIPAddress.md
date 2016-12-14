---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCIPAddress.md
schema: 2.0.0
ms.assetid: B42C7B4D-32E2-48CC-8E31-01E5594D6981
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCIPAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCIPAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCIPAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCIPAddress

## SYNOPSIS
Modifies an allocated IP address by assigning the IP address to an object, or updating the IP address description.

## SYNTAX

```
Set-SCIPAddress [-UserRole <UserRole>] [-VMMServer <ServerConnection>]
 [-AllocatedIPAddress] <AllocatedIPAddress> [-GrantToObjectID <Guid>] [-Description <String>] [-Owner <String>]
 [-ExplicitRevokeRequired <Boolean>] [-DisableReconcile <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCIPAddress** cmdlet modifies an allocated IP address.
You can use **Set-SCIPAddress** to assign an allocated IP address to an object using the *GrantToObjectID* parameter.

## EXAMPLES

### Example 1: Assign an allocated IP address to a load balancer virtual IP
```
PS C:\>$VIP = Get-SCLoadBalancerVIP -Name "LoadBalancerVIP01"
PS C:\> $IPAddressPool = Get-SCStaticIPAddressPool -IPv4 -Subnet "10.0.0.0/24"
PS C:\> $IPAddress = Get-SCIPAddress -StaticIPAddressPool $IPAddressPool -Unassigned
PS C:\> Set-SCIPAddress -AllocatedIPAddress $IPAddress[0] -GrantToObjectID $VIP.ID
```

The first command gets the load balancer virtual IP object named LoadBalancerVIP01 and stores the object in the $VIP variable.

The second command gets the static IP address pool object with the specified IPv4 subnet and stores the object in the $IPAddressPool variable.

The third command gets the unassigned IP address objects for the static IP address pool stored in $IPAddressPool and stores the objects in the $IPAddress variable.

The last command assigns the first unassigned IP address from the addresses stored in $IPAddress to the virtual load balancer ID stored in $VIP.ID.

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

### -Description
Specifies a description for the IP address.

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

### -DisableReconcile


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

### -ExplicitRevokeRequired


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

### -GrantToObjectID
Specifies the ID of an object to which an allocated IP address or MAC address is assigned.

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

### -Owner


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

### -UserRole


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

[Get-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCIPAddress.md)

[Get-SCLoadBalancerVIP](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLoadBalancerVIP.md)

[Get-SCStaticIPAddressPool](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md)

[Grant-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/v1/Grant-SCIPAddress.md)

[Revoke-SCIPAddress](xref:SystemCenter2016/VirtualMachineManager/v1/Revoke-SCIPAddress.md)

