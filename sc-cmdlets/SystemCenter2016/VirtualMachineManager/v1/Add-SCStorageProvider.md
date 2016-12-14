---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: 834B79D9-E506-4F0A-8B51-13A186FD9B70
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCStorageProvider

## SYNOPSIS
Adds a storage provider to VMM.

## SYNTAX

### AddSmisCimXmlProvider (Default)
```
Add-SCStorageProvider [-Fabric] -Name <String> [-Description <String>] -RunAsAccount <RunAsAccount>
 -NetworkDeviceName <String> -TCPPort <UInt32> [-Certificate <ClientCertificate>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### AddSmisWmiProvider
```
Add-SCStorageProvider -Name <String> [-Description <String>] -RunAsAccount <RunAsAccount>
 -ComputerName <String> [-AddSmisWmiProvider] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### AddWindowsNativeWmiProvider
```
Add-SCStorageProvider -Name <String> [-Description <String>] -RunAsAccount <RunAsAccount>
 -ComputerName <String> [-IsNonTrustedDomain] [-AddWindowsNativeWmiProvider] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCStorageProvider** cmdlet adds a storage provider to Virtual Machine Manager (VMM) by providing the connection information required to access the provider over the network.

VMM in System Center 2016 allows you to add a WMI SMI-S provider by using the *AddSmisWmiProvider* parameter.

## EXAMPLES

### Example 1: Add a storage provider by its Fully Qualified Domain Name (FQDN)
```
PS C:\>$RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Add-SCStorageProvider -NetworkDeviceName "http://StorProv01.Contoso.com" -TCPPort 5988 -Name "StorProv01.Contoso.com" -RunAsAccount $RunAsAcct
```

The first command gets the RunAs account named RunAsAccount01 and stores it in the $RunAsAcct variable.

The second command adds the storage provider named StorProv01.Contoso.com using the RunAs account stored in $RunAsAcct.

### Example 2: Add a storage provider by its IP address
```
PS C:\>$RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount02"
PS C:\> Add-SCStorageProvider -NetworkDeviceName "http://10.10.12.23" -TCPPort 5988 -Name "StorProv02.Contoso.com" -RunAsAccount $RunAsAcct02
```

The first command gets the RunAs account named RunAsAccount02 and stores it in the $RunAsAcct variable.

The second command adds the storage provider with an IP address of 10.10.12.23 using the RunAsAccount stored in $RunAsAcct.

### Example 3: Add a WMI SMI-S storage provider
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "AdminRAA"
PS C:\> Add-SCStorageProvider -SmisWmi -Name "StorageProvider01" -RunAsAccount $RunAsAccount -ComputerName "StorageHost01.Contoso.com"
```

The first command gets the Run As account object named AdminRAA and stores the object in the $RunAsAccount variable.

The second command adds the storage provider with the name StorageProvider01 using the Run Account stored in $RunAsAccount.
The SmisWmi parameter indicates that this is an SMI-S storage provider.

## PARAMETERS

### -AddSmisWmiProvider
Indicates that the cmdlet adds an SMIS-based WMI provider.

```yaml
Type: SwitchParameter
Parameter Sets: AddSmisWmiProvider
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AddWindowsNativeWmiProvider
Indicates that the cmdlet adds a Windows native WMI provider implementation.

```yaml
Type: SwitchParameter
Parameter Sets: AddWindowsNativeWmiProvider
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: AddSmisCimXmlProvider
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN (fully qualified domain name) 
- IPv4 or IPv6 address 
- NetBIOS name

```yaml
Type: String
Parameter Sets: AddSmisWmiProvider, AddWindowsNativeWmiProvider
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage provider.

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

### -Fabric
Indicates Fibre Channel fabric.

```yaml
Type: SwitchParameter
Parameter Sets: AddSmisCimXmlProvider
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsNonTrustedDomain
Indicates that the domain is not a trusted Active Directory domain.

```yaml
Type: SwitchParameter
Parameter Sets: AddWindowsNativeWmiProvider
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

### -NetworkDeviceName
Specifies the name of a network device.

```yaml
Type: String
Parameter Sets: AddSmisCimXmlProvider
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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
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

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: UInt32
Parameter Sets: AddSmisCimXmlProvider
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageProvider
This cmdlet returns a **StorageProvider** object.

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageProvider.md)

[Import-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/v1/Import-SCStorageProvider.md)

[Read-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCStorageProvider.md)

[Remove-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCStorageProvider.md)

[Set-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageProvider.md)

