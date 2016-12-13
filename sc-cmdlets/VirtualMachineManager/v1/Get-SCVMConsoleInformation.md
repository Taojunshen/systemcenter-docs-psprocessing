---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: C8A65157-DBAA-448A-9EE6-7342BB2C7DBC
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConsoleInformation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConsoleInformation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMConsoleInformation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMConsoleInformation

## SYNOPSIS
Displays VMM console information about a virtual machine.

## SYNTAX

```
Get-SCVMConsoleInformation [-VM] <VM> [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMConsoleInformation** cmdlet displays Virtual Machine Manager (VMM) console information about a virtual machine.

## EXAMPLES

### Example 1: Get VMM console information for a specified virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Get-SCVMConsoleInformation -VM $VM
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command displays the VMM console information about VM01 to the user.

## PARAMETERS

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:VirtualMachineManager/v1/Get-SCVirtualMachine.md)

