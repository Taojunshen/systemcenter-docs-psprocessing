---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCertificate.md
schema: 2.0.0
ms.assetid: 14F7CDA4-4F58-410C-92FE-B127BCF6B9D1
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCVirtualizationManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCVirtualizationManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCVirtualizationManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCVirtualizationManager

## SYNOPSIS
Adds a VMware vCenter Server to VMM.

## SYNTAX

```
Add-SCVirtualizationManager [-VMMServer <ServerConnection>] [-ComputerName] <String> [-Description <String>]
 -Credential <VMMCredential> [-TCPPort <UInt32>] [-Certificate <ClientCertificate>]
 [-EnableSecureMode <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVirtualizationManager** cmdlet adds a VMware vCenter Server to your Virtual Machine Manager (VMM) environment so that VMM can connect to the vCenter Server and import its data.
After you add the vCenter Server to VMM, you need to add the VMware ESX hosts associated with the vCenter Server before VMM can manage the virtual machines deployed on those hosts.

The default port used to connect to a VMware VirtualCenter Server computer is TCP port 443.

## EXAMPLES

### Example 1: Add a VMware vCenter Server to VMM
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount03"
PS C:\> $Cert = Get-SCCertificate -ComputerName "vCenterServer01.Contoso.com"
PS C:\> Add-SCVirtualizationManager -ComputerName "vCenterServer01.Contoso.com" -Certificate $Cert -TCPPort 443 -Credential $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount03 and stores the object in the $RunAsAccount variable.
The required credentials for this operation are either a local Administrator account or a domain account with administrator rights on the vCenter Server that you want to add as a virtualization manager to VMM.

The second command obtains the security certificate from vCenterrServer01 and stores it in the $Cert variable.

The last command adds the virtualization manager object named vCenterServer01 to the VMM database, imports the security certificate object, and specifies that VMM will use TCP port 443 (the default port) to connect to that server.
As the last command is processed, $Credential provides your Run As credentials to **Add-SCVirtualizationManager**.

### Example 2: Add multiple VMware vCenter Servers to VMM
```
PS C:\>$Credential = Get-SCRunAsAccount -Name "RunAsAccount03" 
PS C:\> $Servers = "vCenterServer01.Contoso.com", "vCenterServer02.Contoso.com"
PS C:\> ForEach ($Server in $Servers) {$Cert = Get-SCCertificate -ComputerName $Server;  Add-SCVirtualizationManager -ComputerName $Server -Certificate $Cert -TCPPort 443 -Credential $Credential}
```

The first command gets the Run As account object named RunAsAccount03 and stores the object in the $RunAsAccount variable.
The required credentials for this operation are either a local Administrator account or a domain account with administrator rights on the vCenter Server that you want to add as a virtualization manager to VMM.

The second command stores the strings "vCenterServer01.Contoso.com" and "vCenterServer02.Contoso.com", which are the names of two VMware vCenter Servers, in the $Servers variable.

The last command adds the two servers to VMM and specifies that VMM will import the security certificates and use TCP port 443 (the default port) to connect to the virtualization manager service on vCenterServer01 and vCenterServer02.
As this command is processed, $Credential provides your Run As credentials to **Add-SCVirtualizationManager**.

For more information about the standard Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

## PARAMETERS

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description for the vCenter Server.

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

### -EnableSecureMode
Indicates whether VMM communicates with VMware ESX hosts and Citrix XenServer hosts in secure mode.
The default value is $True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SecureMode

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

### -TCPPort
Specifies a numeric value that represents a TCP port.

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

### VirtualizationManager
This cmdlet returns a **VirtualizationManager** object.

## NOTES

## RELATED LINKS

[Get-SCCertificate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCCertificate.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualizationManager.md)

[Read-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVirtualizationManager.md)

[Remove-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVirtualizationManager.md)

[Set-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVirtualizationManager.md)

