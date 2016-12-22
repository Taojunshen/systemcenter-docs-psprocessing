---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 23F3169E-8C55-45F7-ABB5-497BCD41CACC
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCustomResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCCustomResource

## SYNOPSIS
Removes a custom resource from the VMM library.

## SYNTAX

```
Remove-SCCustomResource [-CustomResource] <CustomResource> [-Force] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCCustomResource** cmdlet removes a custom resource from the Virtual Machine Manager (VMM) library.

For more information about custom resources, type `Get-Help Set-SCCustomResource`.

## EXAMPLES

### Example 1: Remove a custom resource
```
PS C:\> $CR = Get-SCCustomResource -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "Folder.CR" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Remove-SCCustomResource -CustomResource $CR
```

The first command gets the custom resource object named Folder.CR on LibraryServer01 from the VMM library on VMMServer01 and then stores the object in the $CR variable.

The second command removes the custom resource stored in $CR from the VMM library.

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

### -CustomResource
Specifies a custom resource object.

```yaml
Type: CustomResource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CustomResource
This cmdlet returns a **CustomResource** object.

## NOTES

## RELATED LINKS

[Get-SCCustomResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCustomResource.md)

[Set-SCCustomResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCustomResource.md)

