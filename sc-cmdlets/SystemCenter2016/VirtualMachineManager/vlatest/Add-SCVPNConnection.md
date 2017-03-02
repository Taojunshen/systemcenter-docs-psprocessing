---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 15AE10D1-5CB5-4F03-AAD8-2433553A59AE
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVPNConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVPNConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVPNConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCVPNConnection

## SYNOPSIS
Adds a VPN connection to a virtual machine network.

## SYNTAX

### IPSec (Default)
```
Add-SCVPNConnection [-VMMServer <ServerConnection>] [-VMNetworkGateway] <VMNetworkGateway> [-Name <String>]
 [-Description <String>] [-TargetIPv4VPNAddress <String>] [-TargetIPv6VPNAddress <String>]
 [-EncryptionMethod <VPNEncryptionMethod>] [-IntegrityCheckMethod <VPNIntegrityCheckMethod>]
 [-CipherTransformConstants <VPNCipherTransformConstants>]
 [-AuthenticationTransformConstants <VPNAuthenticationTransformConstants>] [-PFSGroup <VPNPFSGroup>]
 [-DHGroup <VPNDHGroup>] -Protocol <VPNProtocol> [-AuthenticationMethod <VPNAuthenticationMethod>]
 [-Secret <RunAsAccount>] [-Certificate <ClientCertificate>] [-IPSecMainSALifeTimeSeconds <UInt32>]
 [-IPSecMainSALifeTimeKiloBytes <UInt32>] [-IPSecQuickSALifeTimeSeconds <UInt32>]
 [-IPSecQuickSALifeTimeKiloBytes <UInt32>] [-IPSecIdleDisconnectSeconds <UInt32>]
 [-LocalTrafficSelectors <TrafficSelector[]>] [-RemoteTrafficSelectors <TrafficSelector[]>]
 [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### L3
```
Add-SCVPNConnection [-VMMServer <ServerConnection>] [-VMNetworkGateway] <VMNetworkGateway>
 -NextHopNetwork <VMNetwork> [-Name <String>] [-Description <String>] -Protocol <VPNProtocol>
 [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>] -IPAddresses <String[]>
 -PeerIPAddresses <String[]> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### GRE
```
Add-SCVPNConnection [-VMMServer <ServerConnection>] [-VMNetworkGateway] <VMNetworkGateway> [-Name <String>]
 [-Description <String>] [-TargetIPv4VPNAddress <String>] [-TargetIPv6VPNAddress <String>]
 -Protocol <VPNProtocol> [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>]
 [-GRETunnel] [-GREKey <UInt32>] [-GREIPv4Address <String>] [-GREIPv6Address <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVPNConnection** cmdlet adds a virtual private network (VPN) connection to a virtual machine network to establish a site-to-site tunnel from a Virtual Machine Manager (VMM) managed network gateway to another endpoint.

## EXAMPLES

### Example 1: Adds a VPN connection
```
PS C:\> $VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway01"
PS C:\> $RunAsAccount = Get-SCRunAsAccount -ID "972567d5-96ad-472e-9790-831bae5fd69c" 
PS C:\> $VpnConnection = Add-SCVPNConnection -AuthenticationMethod "PSKOnly" -AuthenticationTransformConstants "SHA196" -CipherTransformConstants "AES256" -DHGroup "Group2" -EncryptionMethod "AES256" -IntegrityCheckMethod "SHA1" -PFSGroup "PFS2048" -Protocol "IKEv2" -Name "IPSec" -TargetIPv4VPNAddress "100.100.100.100" -Secret $RunAsAccount -VMNetworkGateway $VmNetworkGateway
```

The first command gets a network gateway named VMGateway01, and then stores it in the $VmNetworkGateway variable.

The second command gets a Run As account, and then stores it in the $RunAsAccount variable.
This account is used to add the VPN connection.

The final command adds a VPN connection to the virtual machine network gateway in $VmNetworkGateway, and then stores it in the $VpnConnection variable.

## PARAMETERS

### -AuthenticationMethod
Specifies a virtual private network (VPN) authentication method.
Valid values are: PSKOnly, MachineCertificates.

```yaml
Type: VPNAuthenticationMethod
Parameter Sets: IPSec
Aliases: 
Accepted values: PSKOnly, MachineCertificates

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationTransformConstants
Specifies a virtual private network (VPN) transform constant.
Valid values are: 

- SHA256128
- MD596
- SHA196
- GCMAES128
- GCMAES192
- GCMAES256

```yaml
Type: VPNAuthenticationTransformConstants
Parameter Sets: IPSec
Aliases: 
Accepted values: SHA256128, MD596, SHA196, GCMAES128, GCMAES192, GCMAES256, SHA256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CipherTransformConstants
Specifies a virtual private network cipher transform constants.
Valid values are: 

- DES
- DES3
- AES128
- AES192
- AES256
- GCMAES128
- GCMAES192
- GCMAES256

```yaml
Type: VPNCipherTransformConstants
Parameter Sets: IPSec
Aliases: 
Accepted values: DES, DES3, AES128, AES192, AES256, GCMAES128, GCMAES192, GCMAES256, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DHGroup
Specifies a virtual private network (VPN) Diffie-Hellman (DH) group.
Valid values are: 

- None
- Group1
- Group2
- Group14
- ECP256
- ECP384
- Group24

```yaml
Type: VPNDHGroup
Parameter Sets: IPSec
Aliases: 
Accepted values: None, Group1, Group2, Group14, ECP256, ECP384, Group24

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the VPN connection.

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

### -EncryptionMethod
Specifies a virtual private network (VPN) encryption method.
Valid values are: 

- DES
- DES3
- AES128
- AES192
- AES256

```yaml
Type: VPNEncryptionMethod
Parameter Sets: IPSec
Aliases: 
Accepted values: DES, DES3, AES128, AES192, AES256, CBCDES, CBCDES3, AES128CBC, AES192CBC, AES256CBC, GCMAES128, GCMAES192, GCMAES256

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GREIPv4Address
Specifies a Generic Route Encapsulation (GRE) IPv4 address.

```yaml
Type: String
Parameter Sets: GRE
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GREIPv6Address
Specifies a GRE IPv6 address.

```yaml
Type: String
Parameter Sets: GRE
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GREKey
Specifies a GRE key.

```yaml
Type: UInt32
Parameter Sets: GRE
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GRETunnel
Indicates that this cmdlet uses a GRE tunnel.

```yaml
Type: SwitchParameter
Parameter Sets: GRE
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPAddresses


```yaml
Type: String[]
Parameter Sets: L3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSecIdleDisconnectSeconds


```yaml
Type: UInt32
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSecMainSALifeTimeKiloBytes


```yaml
Type: UInt32
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSecMainSALifeTimeSeconds


```yaml
Type: UInt32
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSecQuickSALifeTimeKiloBytes


```yaml
Type: UInt32
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPSecQuickSALifeTimeSeconds


```yaml
Type: UInt32
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntegrityCheckMethod
Specifies a virtual private network (VPN) integrity check method.
Valid values are: 

- MD5
- SHA1
- SHA256
- SHA384

```yaml
Type: VPNIntegrityCheckMethod
Parameter Sets: IPSec
Aliases: 
Accepted values: MD5, SHA1, SHA256, SHA384, SHA196

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

### -LocalTrafficSelectors


```yaml
Type: TrafficSelector[]
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaximumBandwidthInboundKbps
Specifies, in kbps, the maximum inbound bandwidth.

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

### -MaximumBandwidthOutboundKbps
Specifies, in kbps, the maximum outbound bandwidth.

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

### -NextHopNetwork
Specifies a **VMNetwork** object.

```yaml
Type: VMNetwork
Parameter Sets: L3
Aliases: 

Required: True
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -PFSGroup
Specifies a virtual private network (VPN) Perfect Forward Secrecy (PFS) group.
Valid values are:

- None
- PFS1
- PFS2
- PFS2048
- ECP256
- ECP384
- PFSMM
- PFS24

```yaml
Type: VPNPFSGroup
Parameter Sets: IPSec
Aliases: 
Accepted values: None, PFS1, PFS2, PFS2048, ECP256, ECP384, PFSMM, PFS24, PFS14

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

### -PeerIPAddresses


```yaml
Type: String[]
Parameter Sets: L3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Protocol
Specifies a VPN protocol.
The acceptable values for this parameter are:

- IKEv2
- L2TP
- PPTP
- GRE

```yaml
Type: VPNProtocol
Parameter Sets: (All)
Aliases: 
Accepted values: IKEv2, L2TP, PPTP, GRE, L3, IPSec

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoteTrafficSelectors


```yaml
Type: TrafficSelector[]
Parameter Sets: IPSec
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

### -Secret
Specifies a Run As account.

To obtain a Run As account, use the **Get-SCRunAsAccount** cmdlet.

```yaml
Type: RunAsAccount
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetIPv4VPNAddress
Specifies a target VPN address in IPv4 format.

```yaml
Type: String
Parameter Sets: IPSec, GRE
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetIPv6VPNAddress
Specifies a target VPN address in IPv6 format.

```yaml
Type: String
Parameter Sets: IPSec, GRE
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

### -VMNetworkGateway
Specifies a virtual machine network gateway object.

To obtain a **VMNetworkGateway** object, use the **Get-SCVMNetworkGateway** cmdlet.

```yaml
Type: VMNetworkGateway
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVPNConnection.md)

[Read-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVPNConnection.md)

[Remove-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVPNConnection.md)

[Set-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVPNConnection.md)

