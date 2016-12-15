---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVirtualizationManager.md
schema: 2.0.0
ms.assetid: 3DC66F00-AF16-4035-B7C5-26E4D941046D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCertificate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCCertificate

## SYNOPSIS
Gets a security certificate object from a VMware vCenter Server, from a VMware ESX host, or from a Citrix XenServer host.

## SYNTAX

### ByRemoteComputer
```
Get-SCCertificate [-VMMServer <ServerConnection>] [-ComputerName] <String> [-TCPPort <UInt32>]
 [<CommonParameters>]
```

### ByLocalFilename
```
Get-SCCertificate [-VMMServer <ServerConnection>] [-Filename] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCCertificate** cmdlet gets a security certificate object from a vCenter Server, from an ESX host, or from a XenServer host.
You can use this cmdlet to import a non-trusted certificate into Virtual Machine Manager (VMM) so that you can use the certificate with the Add-SCVirtualizationManager cmdlet, the Set-SCVirtualizationManager cmdlet, the Add-SCVMHost cmdlet, or the Set-SCVMHost cmdlet.

The certificate is required in order to establish a Secure Socket Layer (SSL) connection between the VMM server and the vCenter Server, ESX host, or XenServer host.

## EXAMPLES

### Example 1: Retrieve the security certificate for the specified VMware vCenter Server
```
PS C:\>Get-SCCertificate -ComputerName "vCenterServer01.Contoso.com"
```

This command gets the security certificate object for the vCenter Server server named vCenterServer01 located in the Contoso.com domain, and displays the security certficate information.

### Example 2: Retrieve the security certificate for a specified VMware ESX host
```
PS C:\>$ESXCert = Get-SCCertificate -ComputerName "ESXHost01.Contoso.com"
PS C:\> $ESXCert | Get-Member
```

The first command gets the security certificate object from the ESX host named ESXHost01 and stores the object in the $ESXCert variable.

The second command passes the contents of $ESXCert to the Get-Member cmdlet, which displays the .NET type and a list of methods and properties for the certificate object.

### Example 3: Retrieve the security certificate for the specified Citrix XenServer host
```
PS C:\>Get-SCCertificate -ComputerName "XenServer01.Contoso.com"
```

This command gets the security certificate object for the XenServer named XenServer01 located in the Contoso.com domain, and displays the security certficate information.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: ByRemoteComputer
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filename
Specifies the name of the certificate that this cmdlet retrieves.

```yaml
Type: String
Parameter Sets: ByLocalFilename
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: UInt32
Parameter Sets: ByRemoteComputer
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

### Certificate
This cmdlet returns a **Certificate** object.

## NOTES

## RELATED LINKS

[Add-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVirtualizationManager.md)

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMHost.md)

[Set-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualizationManager.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHost.md)

