---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: 85D9DD45-7ACC-4ACE-8E42-E80FAAF22A55
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Register-SCVMHost

## SYNOPSIS
Associates a VMware ESX host with VMM as a virtual machine host and specifies credentials to manage the host.

## SYNTAX

```
Register-SCVMHost [-VMHost] <Host> [-Credential <VMMCredential>] [-TCPPort <UInt32>]
 [-Certificate <ClientCertificate>] [-SshTcpPort <UInt32>] [-SshPublicKey <ClientSshPublicKey>]
 [-SshPublicKeyFile <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCVMHost** cmdlet associates a VMware ESX host with Virtual Machine Manager (VMM) as a virtual machine host and specifies the credentials to use with this ESX host.

## EXAMPLES

### Example 1: Set the credentials for a specific VMware ESX host
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "ESX Host Computer Acct"
PS C:\> $ESXHost = Get-SCVMHost -ComputerName "ESXHost02.Contoso.com"
PS C:\> Register-SCVMHost -VMHost $ESXHost -Credential $RunAsAccount
```

The first command gets the Run As account object named ESX Host Computer Acct and stores the object in the $RunAsAccount variable.

The second command gets the ESX host object named ESXHost02 and stores the object in the $ESXHost variable.

The last command associates the VMware ESX host with VMM as a managed host, and specifies that the Run As account stored in $Credential should be used to access ESXHost02.

### Example 2: Set the credentials and certificate for a specific VMware ESX host
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "ESX Host Computer Acct"
PS C:\> $ESXHost = Get-SCVMHost -ComputerName "ESXHost03.contoso.com"
PS C:\> $Cert = Get-SCCertificate -ComputerName "ESXHost03.contoso.com"
PS C:\> Register-SCVMHost -VMHost $ESXHost -Credential $RunAsAccount -Certificate $Cert
```

The first command gets the Run As account object named ESX Host Computer Acct and stores the object in the $RunAsAccount variable.
The required credentials for this operation are either a root account (root/\<password\>) or the account for the VMware delegated administrator defined earlier in VirtualCenter Server for this ESX host.

The second command gets the VMware ESX host object named ESXHost03 and stores the object in the $ESXHost variable.

The third command uses the Get-SCCertificate cmdlet to get the certificate object from ESXHost02 and stores the object in the $Cert variable.

The last command associates this VMware ESX Server with VMM as a managed host and specifies that the credentials used to access ESXHost02 are those stored in $RunAsAccount.

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

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
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

### -SshPublicKey
Specifies the public key used by Secure Shell (SSH) communications.

```yaml
Type: ClientSshPublicKey
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPublicKeyFile
Specifies the path to the public key file for establishing a secured SSH channel with the target hosts.

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

### -SshTcpPort
Specifies the TCP port number used by the SSH protocol.

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
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

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCVMHost.md)

