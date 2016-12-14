---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualNetworkAdapterPortProfileSet.md
schema: 2.0.0
ms.assetid: 6B7D37D0-0515-4D6A-BD07-BDA54EA919BD
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterPortProfileSet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterPortProfileSet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCVirtualNetworkAdapterPortProfileSet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCVirtualNetworkAdapterPortProfileSet

## SYNOPSIS
Removes a virtual network adapter port profile set.

## SYNTAX

```
Remove-SCVirtualNetworkAdapterPortProfileSet [-VMMServer <ServerConnection>]
 [-VirtualNetworkAdapterPortProfileSet] <VirtualNetworkAdapterPortProfileSet> [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCVirtualNetworkAdapterPortProfileSet** cmdlet deletes a virtual network adapter port profile set.

## EXAMPLES

### Example 1: Remove a virtual network adapter port profile set
```
PS C:\>Get-SCVirtualNetworkAdapterPortProfileSet -Name "VirtualNetworkAdapterPortProfSet01" | Remove-SCVirtualNetworkAdapterPortProfileSet
```

This command gets the virtual network adapter port profile set named VirtualNetworkAdapterPortProfSet01 and uses the pipeline operator to pass the object to **Remove-SCVirtualNetworkAdapterPortProfileSet**, which deletes the virtual network adapter port pfofile set object.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -VirtualNetworkAdapterPortProfileSet
Specifies a virtual network adapter port profile set object.

To obtain a virtual network adapter port profile set object, use the Get-SCVirtualNetworkAdapterPortProfileSet cmdlet.

```yaml
Type: VirtualNetworkAdapterPortProfileSet
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

## NOTES

## RELATED LINKS

[Get-SCVirtualNetworkAdapterPortProfileSet](xref:VirtualMachineManager/v1/Get-SCVirtualNetworkAdapterPortProfileSet.md)

[New-SCVirtualNetworkAdapterPortProfileSet](xref:VirtualMachineManager/v1/New-SCVirtualNetworkAdapterPortProfileSet.md)

[Set-SCVirtualNetworkAdapterPortProfileSet](xref:VirtualMachineManager/v1/Set-SCVirtualNetworkAdapterPortProfileSet.md)
