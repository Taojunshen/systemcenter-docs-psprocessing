---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCIPAddress.md
schema: 2.0.0
ms.assetid: B761DE26-F50E-4B8B-8C10-2EEF7BC79C28
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Grant-SCIPAddress.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Grant-SCIPAddress.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Grant-SCIPAddress.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Grant-SCIPAddress

## SYNOPSIS
Allocates a static or virtual IP address from a specified address pool.

## SYNTAX

### Default (Default)
```
Grant-SCIPAddress [-VMMServer <ServerConnection>] -StaticIPAddressPool <StaticIPAddressPool>
 -GrantToObjectType <AllocatedToObjectType> [-IPAddress <String>] [-GrantToObjectID <Guid>]
 [-Description <String>] [-ExplicitRevokeRequired <Boolean>] [-DisableReconcile <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### PublicIPAddress
```
Grant-SCIPAddress [-NetworkController <VirtualSwitchExtensionManager>] [-UserRole <UserRole>]
 [-VMMServer <ServerConnection>] -IPAddress <String> [-Description <String>] [-PublicIPAddress]
 [-Owner <String>] [-ExplicitRevokeRequired <Boolean>] [-DisableReconcile <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Grant-SCIPAddress** cmdlet allocates static IP and virtual IP addresses from a specified address pool.

To grant a specific IP address, use the *IPAddress* parameter.
Otherwise, Virtual Machine Manager (VMM) chooses the IP address from the address pool.

## EXAMPLES

### Example 1: Allocate an IP address
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $vNICs = $VM.VirtualNetworkAdapters
PS C:\> $IPPool = Get-SCStaticIPAddressPool -Name "Production IP Address Pool"
PS C:\> Grant-SCIPAddress -StaticIPAddressPool $IPPool -GrantToObjectType VirtualNetworkAdapter -GrantToObjectID $vNICs[0].ID -Description $VM.Name
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the virtual network adapter objects for virtual machine VM01 and stores the objects in the $vNICs variable.

The third command gets the static IP address pool object named Production IP Address Pool and stores the object in the $IPPool variable.

The last command allocates an IP address from the static IP address pool stored in $IPPool to the first virtual network adapter stored in $vNICs, and supplies VM01 as the description for the allocated IP address.

## PARAMETERS

### -Description
Specifies a description for the object.

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
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GrantToObjectType
Specifies a value for AllocatedToObjectType to which an allocated IP address or virtual IP address is assigned.
The acceptable values for this parameter are:

- VirtualNetworkAdapter
- VIP
- HostNetworkAdapter
- LoadBalancerConfiguration
- VirtualMachine
- HostCluster

```yaml
Type: AllocatedToObjectType
Parameter Sets: Default
Aliases: 
Accepted values: VirtualNetworkAdapter, VIP, HostNetworkAdapter, LoadBalancerConfiguration, VirtualMachine, HostCluster, VMSubnet, NetworkService, NATConnection, NetworkGateway, StorageArray, VMNetworkGateway, None

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddress
Specifies an IPv4 or IPv6 address.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: PublicIPAddress
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

### -NetworkController
Specifies a network controller.

```yaml
Type: VirtualSwitchExtensionManager
Parameter Sets: PublicIPAddress
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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.



Example format: `-Owner "Contoso\PattiFuller"`

Example format: `-Owner "PattiFuller@Contoso"`

```yaml
Type: String
Parameter Sets: PublicIPAddress
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

### -PublicIPAddress


```yaml
Type: SwitchParameter
Parameter Sets: PublicIPAddress
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

### -StaticIPAddressPool
Specifies an IP address pool from which you can assign static IP addresses.

```yaml
Type: StaticIPAddressPool
Parameter Sets: Default
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole


```yaml
Type: UserRole
Parameter Sets: PublicIPAddress
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
* This cmdlet requires a VMM static IP address pool object, which can be retrieved using the Get-SCStaticIPAddressPool cmdlet.

## RELATED LINKS

[Get-SCIPAddress](xref:VirtualMachineManager/v1/Get-SCIPAddress.md)

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Get-SCStaticIPAddressPool](xref:VirtualMachineManager/v1/Get-SCStaticIPAddressPool.md)

[Revoke-SCIPAddress](xref:VirtualMachineManager/v1/Revoke-SCIPAddress.md)

[Set-SCIPAddress](xref:VirtualMachineManager/v1/Set-SCIPAddress.md)

