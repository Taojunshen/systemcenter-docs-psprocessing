---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMMManagedComputer.md
schema: 2.0.0
ms.assetid: F1B2003F-9FDD-4098-8BB6-07BDA43C22ED
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMMManagedComputer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMMManagedComputer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCVMMManagedComputer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMMManagedComputer

## SYNOPSIS
Updates a computer managed by VMM.

## SYNTAX

```
Set-SCVMMManagedComputer [-VMMManagedComputer] <VMMManagedComputer> -Description <String> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMMManagedComputer** cmdlet updates computers that are managed by Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Update the description of a managed computer
```
PS C:\>Get-SCVMMManagedComputer -ComputerName "SPF.Contoso.com" | Set-SCVMMManagedComputer -Description "My CPS SPF-02"
```

This command gets the managed computer object named SPF.Contoso.com and uses the pipeline operator to pass the object to **Set-SCVMMManagedComputer**, which updates the description of the computer.

## PARAMETERS

### -Description
Specifies a description for the managed computer.

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

[Add-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Add-SCVMMManagedComputer.md)

[Get-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Get-SCVMMManagedComputer.md)

[Read-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Read-SCVMMManagedComputer.md)

[Register-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Register-SCVMMManagedComputer.md)

[Remove-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Remove-SCVMMManagedComputer.md)

[Update-SCVMMManagedComputer](xref:VirtualMachineManager/v1/Update-SCVMMManagedComputer.md)

