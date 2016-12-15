---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225374
schema: 2.0.0
ms.assetid: FCC82A76-EE8E-4E77-80AE-C8CBBFE48884
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Restore-SCSMDeletedItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Restore-SCSMDeletedItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Restore-SCSMDeletedItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Restore-SCSMDeletedItem

## SYNOPSIS
Restores items that were previously marked for deletion in Service Manager.

## SYNTAX

```
Restore-SCSMDeletedItem [-DeletedItem] <EnterpriseManagementInstance[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Restore-SCSMDeletedItem** cmdlet restores items that were previously marked for deletion in Service Manager.

## EXAMPLES

### Example 1: Restore a previously deleted item
```
PS C:\>Get-SCSMDeletedItem -DisplayName "Printer7" | Restore-SCSMDeletedItem
```

This command gets the previously marked for deletion item that has the display name Printer7 by using **Get-SCSMDeletedItem**.
The command passes it to the current cmdlet by using the pipeline operator.
That command restores the item.

### Example 2: Restore a previously deleted item and display results
```
PS C:\>Get-SCSMDeletedItem -DisplayName "Printer7" | Restore-SCSMDeletedItem -PassThru
UNCName                PrinterName Description Location
-------                ----------- ----------- --------
\\PrintServer\Printer7 Printer7                Seattle
```

This command gets the previously marked for deletion item that has the display name Printer7 by using **Get-SCSMDeletedItem**.
The command passes it to the current cmdlet by using the pipeline operator.
That command restores the item.
The command specifies the *PassThru* parameter.
The command returns the restored item.

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

### -DeletedItem
Specifies an instance of the deleted item to restore.
To obtain an **EnterpriseManagementInstance** object to use with this cmdlet, use the Get-SCSMDeletedItem cmdlet.

```yaml
Type: EnterpriseManagementInstance[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the restored item.
You can pass this object to other cmdlets.

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

### Microsoft.EnterpriseManagement.Core.Cmdlets.Instances.EnterpriseManagementInstance
You can pipe a deleted item to the *DeletedItem* parameter.
For example, the object that is returned by the **Get-SCSMDeletedItem** cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMDeletedItem](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMDeletedItem.md)

