---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Backup-SCVMMServer.md
schema: 2.0.0
ms.assetid: 03AFB822-0EE6-44DE-811A-A7E15DF4A8C0
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMMServer

## SYNOPSIS
Modifies properties of the VMM management server.

## SYNTAX

```
Set-SCVMMServer [-DiagnosticsAndUsageData <Boolean>] [-VMRCAccessAccount <String>] [-VMRCDefaultPort <UInt32>]
 [-VMConnectDefaultPort <UInt32>] [-LibraryRefresherEnabled <Boolean>] [-LibraryRefresherFrequency <UInt16>]
 [-AutomaticLogicalNetworkCreationEnabled <Boolean>] [-LogicalNetworkMatch <LogicalNetworkMatchOption>]
 [-BackupLogicalNetworkMatch <LogicalNetworkMatchOption>] [-AutomaticVirtualNetworkCreationEnabled <Boolean>]
 [-VMSubnetIDRangeStart <UInt32>] [-VMSubnetIDRangeEnd <UInt32>] [-VMConnectTimeToLiveInMinutes <Int32>]
 [-VMConnectGatewayCertificatePath <String>] [-VMConnectGatewayCertificatePassword <SecureString>]
 [-VMConnectHyperVCertificatePath <String>] [-VMConnectHyperVCertificatePassword <SecureString>]
 [-VMConnectNCCertificatePath <String>] [-VMConnectNCCertificatePassword <SecureString>]
 [-VMConnectHostIdentificationMode <VMConnectHostIDMode>] [-KeyProtectionServerUrl <String>]
 [-AttestationServerUrl <String>] [-ShieldingHelperVhd <VirtualHardDisk>] [-VMMServer <ServerConnection>]
 [-PortACL <PortACL>] [-RemovePortACL] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMMServer** cmdlet modifies one or more properties of the Virtual Machine Manager (VMM) management server.
VMM settings that you can change with the **Set-SCVMMServer** cmdlet include the following:

Configure Federated Authentication

You can use the parameters provided with **Set-SCVMMServer** to configure Federated Authentication.
Federated authentication allows a user to connect to the console of a virtual machine without having credentials on the Hyper-V host computer.
Use the New-SCVMConnectFedAuth cmdlet to issue Federated Authentication tokens.

Microsoft Customer Experience Improvement Program (CEIP) Participation

You can use **Set-SCVMMServer** to specify whether to enable Service Quality Metrics (SQM) for this VMM management server.

Library Settings

You can use **Set-SCVMMServer** to specify whether the VMM library refresher is enabled and, if so, how often objects in the library are refreshed.

Network Settings

You can use the **Set-VMMServer** cmdlet to configure how to match logical networks.
You can also enable creation of logical and virtual networks automatically.

Remote Control

You can use **Set-SCVMMServer** to configure the default remote control port to use when connecting to virtual machines (VMConnect).

Contact for Self-Service Users

You can use **Set-SCVMMServer** to specify the e-mail address of an administrator that supports self-service users.

Guest Agent Settings


You can use **Set-SCVMMServer** to select the method used to communicate with the VMM guest agent: FQDN or IP Address.

## EXAMPLES

### Example 1: Set the frequency at which the library is refreshed
```
PS C:\>Set-SCVMMServer -VMMServer "VMMServer01.Contoso.com" -LibraryRefresherEnabled $True -LibraryRefresherFrequency 24
```

This command enables library refreshing for VMMServer01 and sets the refreshing frequency rate to every 24 hours.

### Example 2: Opt out of the Customer Experience Improvement Program
```
PS C:\>Set-SCVMMServer -VMMServer "VMMServer01.Contoso.com" -CEIPOptIn $False
```

This command opts out of participation in the Microsoft Customer Experience Improvement Program (CEIP) by setting the *CEIPOptIn* parameter to $False on VMMServer01.

### Example 3: Specify a self-service contact e-mail address
```
PS C:\>Set-SCVMMServer -VMMServer "VMMServer01.Contoso.com" -SelfServiceContactEmail "AdminHelp@Contoso.com"
```

This command sets the self service contact e-mail address to AdminHelp@Contoso.com on VMMServer01.

## PARAMETERS

### -AttestationServerUrl
Specifies the URL of the attestation server.

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

### -AutomaticLogicalNetworkCreationEnabled
Indicates whether logical networks are created automatically.
When set to $True, a new logical network is created, based on the logical network matching settings, if the host network network adapter is not associated with a logical network.

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

### -AutomaticVirtualNetworkCreationEnabled
Indicates whether virtual networks are created automatically.
When set to $True, if a host has one network adapter for placement associated with a logical network, but no virtual networks attached to the adapter, a new virtual network is created.

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

### -BackupLogicalNetworkMatch
Specifies the network matching method to use if the primary network matching method is not available.

```yaml
Type: LogicalNetworkMatchOption
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, FirstDNSSuffixLabel, DNSSuffix, NetworkConnectionName, VirtualNetworkSwitchName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiagnosticsAndUsageData


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

### -KeyProtectionServerUrl
Specifies the URL for the Key Protection Server (KPS).

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

### -LibraryRefresherEnabled
Indicates, when set to $True, that VMM library objects are refreshed.

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

### -LibraryRefresherFrequency
Specifies, in hours, the frequency at which objects in the VMM library are refreshed.
The default setting is 1 hour.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LogicalNetworkMatch
Specifies the logical network matching method to use for automatically creating logical networks.
The acceptable values for this parameter are:

- Disabled
- FirstDNSSuffixLabel
- DNSSuffix
- NetworkConnectionName
- VirtualNetworkSwitchName

```yaml
Type: LogicalNetworkMatchOption
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, FirstDNSSuffixLabel, DNSSuffix, NetworkConnectionName, VirtualNetworkSwitchName

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

### -PortACL
Specifies a port ACL object.

```yaml
Type: PortACL
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemovePortACL
Indicates that this operation removes the port access control list (ACL).

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

### -ShieldingHelperVhd


```yaml
Type: VirtualHardDisk
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectDefaultPort
Specifies the default value for the TCP port used for Virtual Machine Connection (VMConnect) sessions on all Hyper-V hosts managed by this VMM server.
Typically, the default port is 2179, but you can use this parameter to change the default.
This parameter does not apply to VMware ESX Server hosts or Citrix XenServer hosts.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectGatewayCertificatePassword
Specifies the gateway certificate password as a secure string.
You must specify a value for this parameter when the *VMConnectGatewayCertificatePath* parameter is specified.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectGatewayCertificatePath
Specifies the path to a private key certificate (.pfx file).

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

### -VMConnectHostIdentificationMode
Specifies how the Hyper-V host is identified.
The acceptable values for this parameter are:

 -- FQDN
- IPv4
- IPv6
- HostName

```yaml
Type: VMConnectHostIDMode
Parameter Sets: (All)
Aliases: 
Accepted values: FQDN, IPv4, IPv6, HostName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectHyperVCertificatePassword
Specifies the Hyper-V certificate password as a secure string.
You must specify a value for this parameter when the *VMConnectHyperVCertificatePath* parameter is specified.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectHyperVCertificatePath
Specifies the path to a private key certificate (.pfx file).

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

### -VMConnectNCCertificatePassword
```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMConnectNCCertificatePath
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

### -VMConnectTimeToLiveInMinutes
Specifies, in minutes, the validity period for which the tokens are issues.
Valid values are 1 to 60.

```yaml
Type: Int32
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

### -VMRCAccessAccount
Specifies the account to use when connecting to a virtual machine by using Virtual Machine Remote Control (VMRC).

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

### -VMRCDefaultPort
Specifies the default port to use when connecting to a virtual machine by using VMRC.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnetIDRangeEnd
Specifies the ending ID for a virtual machine subnet ID range.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSubnetIDRangeStart
Specifies the starting ID for a virtual machine subnet ID range.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMMServer
This cmdlet returns a **VMMServer** object.

## NOTES

## RELATED LINKS

[Backup-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Backup-SCVMMServer.md)

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

