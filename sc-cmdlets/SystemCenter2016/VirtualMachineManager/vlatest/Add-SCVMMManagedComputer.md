---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D2E1ED5F-9990-483C-B2F4-9C0F6360D21D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCVMMManagedComputer

## SYNOPSIS
Adds a managed computer to VMM.

## SYNTAX

```
Add-SCVMMManagedComputer [-Description <String>] [-ComputerName] <String> -Credential <VMMCredential>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCVMMManagedComputer** cmdlet adds a managed computer to Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Add a new SPF server into VMM as a managed computer
```
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "RunAsAcct01"
PS C:\> Add-SCVMMManagedComputer -ComputerName "SPF.Contoso.com" -Description "SPF" -Credential $RunAsAccount
```

The first command gets the Run As account object named RunAsAcct01 and stores the object in the $RunAsAccount variable.

The second command adds the SPF server named SPF.Contoso.com to VMM as a managed computer.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
-  NetBIOS name

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
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

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
Specifies a description for the managed computer.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMMManagedComputer
This cmdlet returns a **VMMManagedComputer** object.

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVMMManagedComputer.md)

[Register-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMMManagedComputer.md)

[Remove-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMMManagedComputer.md)

[Set-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMManagedComputer.md)

[Update-SCVMMManagedComputer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCVMMManagedComputer.md)

