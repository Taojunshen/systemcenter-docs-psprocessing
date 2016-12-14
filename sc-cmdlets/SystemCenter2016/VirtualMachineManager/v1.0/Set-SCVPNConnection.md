---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVPNConnection.md
schema: 2.0.0
ms.assetid: 0BD25D24-D225-46CA-A232-67390F95A79B
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVPNConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVPNConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVPNConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVPNConnection

## SYNOPSIS
Sets the properties of a VPN connection.

## SYNTAX

### IPSec (Default)
```
Set-SCVPNConnection [-VMMServer <ServerConnection>] [-VPNConnection] <VPNConnection> [-Name <String>]
 [-Description <String>] [-TargetIPv4VPNAddress <String>] [-TargetIPv6VPNAddress <String>]
 [-EncryptionMethod <VPNEncryptionMethod>] [-IntegrityCheckMethod <VPNIntegrityCheckMethod>]
 [-CipherTransformConstants <VPNCipherTransformConstants>]
 [-AuthenticationTransformConstants <VPNAuthenticationTransformConstants>] [-PFSGroup <VPNPFSGroup>]
 [-DHGroup <VPNDHGroup>] [-AuthenticationMethod <VPNAuthenticationMethod>] [-Secret <RunAsAccount>]
 [-Certificate <ClientCertificate>] [-IPSecMainSALifeTimeSeconds <UInt32>]
 [-IPSecMainSALifeTimeKiloBytes <UInt32>] [-IPSecQuickSALifeTimeSeconds <UInt32>]
 [-IPSecQuickSALifeTimeKiloBytes <UInt32>] [-IPSecIdleDisconnectSeconds <UInt32>]
 [-LocalTrafficSelectors <TrafficSelector[]>] [-RemoveLocalTrafficSelectors]
 [-RemoteTrafficSelectors <TrafficSelector[]>] [-RemoveRemoteTrafficSelectors]
 [-Status <GatewayConnectionStatus>] [-MaximumBandwidthInboundKbps <UInt64>]
 [-MaximumBandwidthOutboundKbps <UInt64>] [-RemoveMaximumBandwidthInbound] [-RemoveMaximumBandwidthOutbound]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### L3
```
Set-SCVPNConnection [-VMMServer <ServerConnection>] [-VPNConnection] <VPNConnection>
 [-NextHopNetwork <VMNetwork>] [-Name <String>] [-Description <String>] [-Status <GatewayConnectionStatus>]
 [-MaximumBandwidthInboundKbps <UInt64>] [-MaximumBandwidthOutboundKbps <UInt64>]
 [-RemoveMaximumBandwidthInbound] [-RemoveMaximumBandwidthOutbound] [-IPAddresses <String[]>]
 [-PeerIPAddresses <String[]>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### GRE
```
Set-SCVPNConnection [-VMMServer <ServerConnection>] [-VPNConnection] <VPNConnection> [-Name <String>]
 [-Description <String>] [-TargetIPv4VPNAddress <String>] [-TargetIPv6VPNAddress <String>]
 [-Status <GatewayConnectionStatus>] [-MaximumBandwidthInboundKbps <UInt64>]
 [-MaximumBandwidthOutboundKbps <UInt64>] [-RemoveMaximumBandwidthInbound] [-RemoveMaximumBandwidthOutbound]
 [-GRETunnel] [-GREKey <UInt32>] [-GREIPv4Address <String>] [-GREIPv6Address <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVPNConnection** cmdlet updates the properties of a virtual private network (VPN) connection.

## EXAMPLES

### Example 1: Modify a VPN connection
```
PS C:\>$VmNetworkGateway = Get-SCVMNetworkGateway -Name "VMGateway01"
PS C:\> $VPNConnection = Get-SCVPNConnection -VMNetworkGateway $VmNetworkGateway -Name "VPN01"
PS C:\> $RunAsAccount = Get-SCRunAsAccount -ID "972567d5-96ad-472e-9790-831bae5fd69c" 
PS C:\> $VpnConnection = Set-SCVPNConnection -AuthenticationMethod "PSKOnly" -AuthenticationTransformConstants "SHA196" -CipherTransformConstants "AES256" -DHGroup "Group2" -EncryptionMethod "AES256" -IntegrityCheckMethod "SHA1" -PFSGroup "PFS2048" -Name "IPSec" -TargetIPv4VPNAddress "100.100.100.200" -VPNConnection $VPNConnection -Secret $RunAsAccount
```

The first command gets a network gateway named VMGateway01, and then stores it in the $VmNetworkGateway variable.

The second command gets a VPN connection on the gateway in $VmNetworkGateway, and then stores it in the $VPNConnection variable.

The third command gets a Run As account, and then stores it in the $RunAsAccount variable.
This account is used to modify the VPN connection.

The final command modifies the VPN connection in $VPNConnection.
It specifies new values for several parameters.

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

Required: False
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

Required: False
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

### -RemoveLocalTrafficSelectors


```yaml
Type: SwitchParameter
Parameter Sets: IPSec
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveMaximumBandwidthInbound


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

### -RemoveMaximumBandwidthOutbound


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

### -RemoveRemoteTrafficSelectors


```yaml
Type: SwitchParameter
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

To obtain a Run As account, use the Get-SCRunAsAccount cmdlet.

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

### -Status


```yaml
Type: GatewayConnectionStatus
Parameter Sets: (All)
Aliases: 
Accepted values: Error, Enabled, Disabled

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

### -VPNConnection
Specifies a virtual private network (VPN) connection object.

To obtain a VPN connection object, use the Get-SCVPNConnection cmdlet.

```yaml
Type: VPNConnection
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVPNConnection.md)

[Get-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVPNConnection.md)

[Read-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Read-SCVPNConnection.md)

[Remove-SCVPNConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVPNConnection.md)

