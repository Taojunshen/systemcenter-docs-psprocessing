---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: A98B7432-F2E1-44A2-894D-49319EEADDF4
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMHost

## SYNOPSIS
Removes a virtual machine host from VMM.

## SYNTAX

### NormalRemoval (Default)
```
Remove-SCVMHost [-VMHost] <Host> [-VMMServer <ServerConnection>] [-Credential <VMMCredential>]
 [-RemoveHostWithVMs] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ForceRemoval
```
Remove-SCVMHost [-VMHost] <Host> [-VMMServer <ServerConnection>] [-Force] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMHost** cmdlet removes one or more virtual machine hosts from Virtual Machine Manager (VMM).
The **Remove-SCVMHost** cmdlet operates as follows:

- Host Server Only. If this computer is a Hyper-V host but is not also a library server, the host object is removed from the VMM database, and the VMM agent software is uninstalled from the physical host server.

If the host is a VMware ESX host or a Citrix XenServer host, the host object is removed from the VMM database.
VMM does not install an agent on ESX hosts or XenServer hosts.

- Host And Library Server. If this computer is a Hyper-V host and is also a library server, this command removes only the host functionality but leaves the library server feature in place. That is, the host object is removed from the VMM database, but the VMM agent software is not uninstalled from the physical server. The library server object remains in the database.

If the host is an ESX host, it can function only as a virtual machine host in VMM.
It cannot be both a host and a library server.

- Credentials. If a Hyper-V host is joined to an Active Directory domain, you must provide credentials for an account with appropriate permissions to remove that host computer from VMM.

You do not need to provide Active Directory credentials to remove a perimeter network host, an ESX host, or a XenServer host from VMM.

- Virtual Machines. When you remove a host, the host is no longer managed by VMM. However, any virtual machines on the host server will not be removed or disassociated from the server. Any running virtual machines are not shut down. Although the virtual machines are no longer managed by VMM, they are not affected in any other way.
- Forced Removal. You can use the *Force* parameter with the **Remove-SCVMHost** cmdlet to remove a virtual machine host from VMM when you do not have appropriate credentials to manage that host or when the VMM server can no longer communicate with that host.

When you specify the *Force* parameter, VMM does not ask or check for credentials, nor will VMM attempt to connect to the host and uninstall the VMM agent.
Hence, using the *Force* parameter is recommended only when removing stale host records from the VMM database.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a specific domain-joined host from VMM
```
PS C:\>$Credential = Get-Credential
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> Remove-SCVMHost -VMHost $VMHost -Credential $Credential -Confirm
```

The first command uses the Get-Credential cmdlet to prompt you to supply a user name and password and stores the provided credentials in the $Credential variable.
The required credentials for this operation are a domain account with administrator rights to remove a Windows-based host server joined to an Active Directory domain from VMM.

The second command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The third command removes the host object stored in $VMHost.
As this command is processed, $Credential provides credentials to **Remove-VMHost**, and the *Confirm* parameter prompts you to confirm that you do want to remove this host from VMM.

### Example 2: Remove all hosts that are not nodes in a host cluster from VMM
```
PS C:\>Get-SCVMHost | where {$_.HostCluster -eq $NULL} | where {$_.VirtualizationPlatform -eq "VMwareESX" -or $_.PerimeterNetworkHost -eq 1 -or $_.NonTrustedDomainHost -eq 1} | Remove-SCVMHost -Confirm
PS C:\> $Credential = Get-Credential
PS C:\> Get-VMHost | where {$_.HostCluster -eq $NULL -and $_.VirtualizationPlatform -ne "VMwareESX" -and $_.PerimeterNetworkHost -eq 0 -and $_.NonTrustedDomainHost -eq 0} | Remove-VMHost -Credential $Credential -Confirm
```

The first command gets all host objects, excludes any hosts that are nodes in a host cluster, selects only those objects that represent VMware ESX hosts, perimeter network hosts, or non-trusted domain hosts, and then removes those objects from VMM if you confirm that you want to remove them.
Credentials are not required to remove these hosts.

The second command prompts you to supply a user name and password for an account with permissions to remove domain-joined Windows hosts from VMM and stores your credentials in $Credential.

The last command gets all domain-joined Windows-based host objects that are not part of a host cluster and passes the objects to the **Remove-VMHost** cmdlet.
As this command is processed, $Credential provides your credentials to **Remove-VMHost**, and the *Confirm* parameter prompts you to confirm that you do want to remove these hosts from VMM.

### Example 3: Remove a specific host that you can no longer access from VMM
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost03"
PS C:\> Remove-SCVMHost -VMHost $VMHost -Force -Confirm
```

The first command gets the host object named VMHost03 and stores the object in the $VMHost variable.

The second command switches on the *Force* parameter to ensure that VMHost03 is removed from the VMM database.
Credentials are not needed for this operation.
The *Confirm* parameter prompts you to confirm that you do want to remove this host.

Note: You can use the *Force* parameter to remove a host from VMM when you do not have the credentials for that host or when the VMM server can no longer communicate with that host.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Parameter Sets: NormalRemoval
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: ForceRemoval
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

### -RemoveHostWithVMs
For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: SwitchParameter
Parameter Sets: NormalRemoval
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVMHost.md)

[New-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md)

[Repair-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCVMHost.md)

