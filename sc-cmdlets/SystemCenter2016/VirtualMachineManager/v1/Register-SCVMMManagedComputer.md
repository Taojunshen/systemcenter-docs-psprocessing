---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMMManagedComputer.md
schema: 2.0.0
ms.assetid: 130C3630-D5D8-4EE7-9833-DC9205E553B3
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Register-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Register-SCVMMManagedComputer

## SYNOPSIS
Reassociates a managed computer on which VMM agent software is installed with a different VMM management server.

## SYNTAX

```
Register-SCVMMManagedComputer [-VMMManagedComputer] <VMMManagedComputer> -Credential <VMMCredential>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCVMMManagedComputer** cmdlet reassociates a managed computer on which Virtual Machine Manager (VMM) agent software is installed with a different VMM management server.

When you initially add a host or library server to VMM, the host or library server is associated with the VMM management server that provides the VMM database that you added the host or library server to.
The VMM database might be installed in a Microsoft SQL Server database on the VMM management server itself or on a remote computer running SQL Server.

After a host or library server is added to (and therefore associated with) a VMM management server, it cannot communicate with any other VMM management server.
However, you can re-associate it with a different VMM management server, as described in the following scenarios.

Scenario 1: Disaster Recovery


In this scenario, VMMServerA fails, or the VMM service running on VMMServerA fails.
You might already have VMMServerB available as a backup VMM management server.
If not, you can install the VMM service on VMMServerB.
At this point, the VMM database might be on VMMServerB, or, if you keep the database on a separate SQL Server, you can now point VMMServerB to the VMM database on that SQL Server.

However, although you now have a functioning VMM management server (VMMServerB) and database, hosts and library servers that were managed by VMMServerA are still configured to communicate with VMMServerA.
VMMServerB recognizes these managed computers, but they are in an Access Denied state.
At this point, you can use **Reassociate-SCVMMManagedComputer** to re-associate computers that were managed by VMMServerA with VMMServerB.

Scenario 2: Re-Organizing Server Groupings


In this scenario, VMMServerA and VMMServerB are two existing VMM management servers that manage different sets of hosts and library servers.
If, for example, VMHost01 is currently managed by VMMServerA, you can add VMHost01 to VMMServerB by using the Add-SCVMHost cmdlet with the *Reassociate* parameter.
If you do this, the state of VMHost01 on VMMServerA is now Access Denied and its state on VMMServerB is Responding.
VMHost01 is now managed by VMMServerB, so you can remove it from VMMServerA.

You can also use **Reassociate-SCVMMManagedComputer** to reassociate Host01 with VMMServerA.

## EXAMPLES

### Example 1: Re-associate all unassociated managed computers with a specific VMM server
```
PS C:\>Get-VMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> $Credential = Get-Credential
PS C:\> Get-VMMManagedComputer | where {$_.State -eq "NotResponding"} | Register-SCVMMManagedComputer -Credential $Credential
```

The first command connects to VMMServer01 in the Contoso.com domain.

The second command uses Get-Credential to prompt you to supply a user name and password and stores your credentials in the $Credential variable.
The required credentials for this operation are a domain account with administrator rights on the host server that you want to reassociate with a specific VMM server and the password for that account.

The last command gets all managed computers from VMMServer01 and selects only those objects that are in the Not Responding state.
Then, it passes these objects to the **Register-SCVMMManagedComputer** cmdlet which changes the association of the objects to VMMerver01.
As this command is processed, $Credential provides your credentials to **Register-SCVMMManagedComputer**.

## PARAMETERS

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

### -VMMManagedComputer
Specifies a computer object that is managed by VMM.

```yaml
Type: VMMManagedComputer
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

### VMMManagedComputer
This cmdlet returns a **VMMManagedComputer** object.

## NOTES

## RELATED LINKS

[Add-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMMManagedComputer.md)

[Get-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMMManagedComputer.md)

[Remove-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMMManagedComputer.md)

[Set-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMMManagedComputer.md)

[Update-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1/Update-SCVMMManagedComputer.md)

