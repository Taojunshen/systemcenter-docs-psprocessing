---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPhysicalComputerProfile.md
schema: 2.0.0
ms.assetid: 5B72BFE6-0BDF-4451-A310-F88C80FE3884
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCPhysicalComputerProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCPhysicalComputerProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCPhysicalComputerProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCPhysicalComputerProfile

## SYNOPSIS
Removes a physical computer profile from VMM.

## SYNTAX

```
Remove-SCPhysicalComputerProfile [-PhysicalComputerProfile] <PhysicalComputerProfile> [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCPhysicalComputerProfile** cmdlet removes a physical computer profile from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove a physical computer profile from VMM
```
PS C:\>$PCP = Get-SCPhysicalComputerProfile -Name "Windows Server 2012 R2" 
PS C:\> Remove-SCPhysicalComputerProfile -PhysicalComputerProfile $PCP
```

The first command gets the physical computer profile named Windows Server 2012 R2 by using the Get-SCPhysicalComputerProfile cmdlet.
The command stores it in the $PCP variable.

The second command deletes the physical computer profile in $PCP from VMM.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### PhysicalComputerProfile
This cmdlet returns a **PhysicalComputerProfile** object.

## NOTES

## RELATED LINKS

[Get-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Get-SCPhysicalComputerProfile.md)

[New-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/New-SCPhysicalComputerProfile.md)

[Set-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Set-SCPhysicalComputerProfile.md)

