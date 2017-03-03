---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9529348E-2E70-4DAA-8C4D-14E2A9656C5C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCOpsMgrConnection

## SYNOPSIS
Removes the Operations Manager connection from VMM.

## SYNTAX

```
Remove-SCOpsMgrConnection [-VMMServer <ServerConnection>] [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOpsMgrConnection** cmdlet removes the existing Operations Manager connection from Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Remove the Operations Manager connection from VMM
```
PS C:\> Remove-SCOpsMgrConnection
```

This command removes the Operations Manager connection from VMM.

### Example 2: Remove an Operations Manager connection that is not accessible from VMM
```
PS C:\> Remove-SCOpsMgrConnection -Force
```

This command removes an Operations Manager connection from VMM when the Operations Manager server is unavailable or no longer accessible from VMM.

Note: Removing the connection to an Operations Manager server that is unavailable or no longer accessible from VMM will not remove VMM-related artifacts, such as internal connectors, from Operations Manager.

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

[Get-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md)

[New-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md)

[Set-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md)

[Write-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Write-SCOpsMgrConnection.md)

