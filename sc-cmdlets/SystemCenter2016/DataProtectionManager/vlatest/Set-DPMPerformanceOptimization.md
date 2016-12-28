---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EC250290-B9B0-44D4-BEC0-7CBABEC6C8BE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMPerformanceOptimization.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMPerformanceOptimization.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMPerformanceOptimization.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMPerformanceOptimization

## SYNOPSIS
Enables or disables on-the-wire compression for a DPM protection group.

## SYNTAX

### EnableCompression
```
Set-DPMPerformanceOptimization [-ProtectionGroup] <ProtectionGroup> [-EnableCompression] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DisableCompression
```
Set-DPMPerformanceOptimization [-ProtectionGroup] <ProtectionGroup> [-DisableCompression] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMPerformanceOptimization** cmdlet enables or disables on-the-wire compression of data for a System Center 2016 - Data Protection Manager (DPM) protection group.
First, get a protection group by using the Get-DPMProtectionGroup cmdlet.
Then, use the Get-DPMModifiableProtectionGroup cmdlet to let you change that protection group.

On-the-wire compression decreases the amount of data transferred during replica creation, synchronization, and consistency check operations.
On-the-wire compression increases CPU usage on both the DPM server and on protected computers.

## EXAMPLES

### Example 1: Enable compression for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer07"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup
PS C:\> Set-DPMPerformanceOptimization -ProtectionGroup $MPGroup -EnableCompression
```

The first command uses the **Get-DPMProtectionGroup** cmdlet to get the protection group for the DPM server named DPMServer07, and stores that object in the $PGroup variable.

The second command uses the **Get-DPMModifiableProtectionGroup** cmdlet to get the protection group in $PGroup in an editable format, and then stores that object in the $MPGroup variable.

The third command enables compression for the protection group in $MPGroup.

## PARAMETERS

### -DisableCompression
Indicates that the cmdlet disables on-the-wire compression of data.

```yaml
Type: SwitchParameter
Parameter Sets: DisableCompression
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableCompression
Indicates that the cmdlet enables on-the-wire compression of data.

```yaml
Type: SwitchParameter
Parameter Sets: EnableCompression
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProtectionGroup
Specifies a protection group that this cmdlet modifies.
To obtain a **ProtectionGroup** object, use the **Get-DPMProtectionGroup** cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### ProtectionGroup

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)

