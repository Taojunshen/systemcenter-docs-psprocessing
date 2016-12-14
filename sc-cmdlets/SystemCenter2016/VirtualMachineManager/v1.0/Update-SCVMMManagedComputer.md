---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMMManagedComputer.md
schema: 2.0.0
ms.assetid: F9BDB12E-7F1E-47C6-BD3E-C804882CC17E
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Update-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Update-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Update-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCVMMManagedComputer

## SYNOPSIS
Updates VMM agent software installed on a Windows-based managed computer.

## SYNTAX

```
Update-SCVMMManagedComputer [-VMMManagedComputer] <VMMManagedComputer> -Credential <VMMCredential>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCVMMManagedComputer** cmdlet updates Virtual Machine Manager (VMM) agent software installed on a Windows-based managed computer to the current version of the software.

If you upgrade your VMM management server to a later version of the VMM service, afterward you can use this command to update agent software on computers that are managed by that VMM management server.

Managed computers that you can update by using this cmdlet include: 


- Hyper-V hosts
- Windows-based library servers
- Windows-based P2V source computers

You can use the **Update-SCVMMManagedComputer** cmdlet to update the VMM agent software on domain-joined trusted hosts and non-trusted domain-joined hosts, but not on hosts located on a perimeter network.

## EXAMPLES

### Example 1: Update all managed computers
```
PS C:\>$Credential = Get-Credential
PS C:\> Get-SCVMMManagedComputer | ForEach { Update-SCVMMManagedComputer -VMMManagedComputer $_ -Credential $Credential -RunAsynchronously }
```

The first command prompts you to provide credentials with appropriate permissions to perform this operation and stores the credentials in the $Credential variable.

The second command gets all computer objects that are currently managed by VMM and passes each object to the ForEach-Object cmdlet, which uses the Update-SCVMMManagedComputer cmdlet to update the agent software on each managed computer.
As this command is processed, $Credential provides your credentials to **Update-SCVMMManagedComputer**.
Note: This example assumes that no managed computers are located in a perimeter network.

For more information about the **ForEach-Object** cmdlet, type `Get-Help ForEach-Object`.

### Example 2: Update a specific host
```
PS C:\>$Credential = Get-Credential
PS C:\> $VMMManagedHost = Get-SCVMMManagedComputer -ComputerName "VMHost01.Contoso.com"
PS C:\> Update-SCVMMManagedComputer -VMMManagedComputer $VMMManagedHost -Credential $Credential
```

The first command prompts you to provide credentials with appropriate permissions to perform this operation and stores the credentials in the $Credential variable.

The second command gets the managed host object named VMHost01 and stores the object in the $VMMManagedHost variable.

The last command updates the agent software on VMHost01.
As this command is processed, $Credential provides your credentials to **Update-SCVMMManagedComputer**.

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

## NOTES

## RELATED LINKS

[Add-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCVMMManagedComputer.md)

[Get-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Read-SCVMMManagedComputer.md)

[Register-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Register-SCVMMManagedComputer.md)

[Remove-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCVMMManagedComputer.md)

[Set-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCVMMManagedComputer.md)

