---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHost.md
schema: 2.0.0
ms.assetid: C995D7FD-0BA9-4753-87EE-1DFBCACE39B3
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Repair-SCVMHost.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Repair-SCVMHost

## SYNOPSIS
Starts remediation steps on a failed host for a set of known failure conditions.

## SYNTAX

```
Repair-SCVMHost [-VMHost] <Host> [-Credential <VMMCredential>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-SCVMHost** cmdlet starts a set of remediation steps on a host in failed state for a set of known failure conditions.

## EXAMPLES

### Example 1: Start remediation steps for a failed host object
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Get-SCVMHost -ComputerName "VMHost01" | Repair-SCVMHost -Credential $RunAsAccount
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $RunAsAccount variable.

The second command gets the host object named VMHost01 and uses the pipeline operator to pass the object to the **Repair-SCVMHost** cmdlet which triggers the remediation steps for known failure causes, using the credentials supplied in $RunAsAccount.

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
Parameter Sets: (All)
Aliases: 

Required: False
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

### Host
This cmdlet returns a **Host** object.

## NOTES

## RELATED LINKS

[Add-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCVMHost.md)

[Disable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Disable-SCVMHost.md)

[Enable-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Enable-SCVMHost.md)

[Get-SCCertificate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCCertificate.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md)

[Move-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Move-SCVMHost.md)

[Read-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCVMHost.md)

[Remove-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCVMHost.md)

[Register-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Register-SCVMHost.md)

[Restart-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Restart-SCVMHost.md)

[Set-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCVMHost.md)

[Start-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCVMHost.md)

[Stop-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Stop-SCVMHost.md)

