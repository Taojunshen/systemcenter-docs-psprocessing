---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMMManagedComputer.md
schema: 2.0.0
ms.assetid: 7FF45129-EA83-415B-9200-F0B0B5BA94E5
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVMMManagedComputer

## SYNOPSIS
Removes a computer from VMM management.

## SYNTAX

```
Remove-SCVMMManagedComputer [-VMMManagedComputer] <VMMManagedComputer> -Credential <VMMCredential>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVMMManagedComputer** cmdlet removes computer objects from Virtual Machine Manager (VMM) management.

## EXAMPLES

### Example 1: Remove a managed computer object
```
PS C:\>$RunAsAccount = Get-SCRunAsAccount -Name "RunAsAcct01"
PS C:\> Get-SCVMMManagedComputer -ComputerName "SPF.Contoso.com" | Remove-SCVMMManagedComputer -Credential $RunAsAccount
```

The first command gets the Run as account object named RunAsAcct01 and stores the object in the $RunAsAccount variable.

The second command gets the managed computer object named SPF.Contoso.com and uses the pipeline operator to pass the object to **Remove-SCVMMManagedComputer**, which removes the computer from VMM management.

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

[Add-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Add-SCVMMManagedComputer.md)

[Get-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Get-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Read-SCVMMManagedComputer.md)

[Register-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Register-SCVMMManagedComputer.md)

[Set-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Set-SCVMMManagedComputer.md)

[Update-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Update-SCVMMManagedComputer.md)
