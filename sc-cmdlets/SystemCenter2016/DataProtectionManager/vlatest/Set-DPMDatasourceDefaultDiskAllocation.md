---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E155743A-4563-40F0-B999-87AEDBCEA22D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDefaultDiskAllocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDefaultDiskAllocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDefaultDiskAllocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMDatasourceDefaultDiskAllocation

## SYNOPSIS
Retrieves the amount of disk space that is allocated to protected data.

## SYNTAX

```
Set-DPMDatasourceDefaultDiskAllocation [-Datasource] <Datasource[]> [-CalculateSize] [-Async] [-Tag <Object>]
 [-PrimaryDpmServer] [-CalculateShrinkThresholds] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMDatasourceDefaultDiskAllocation** cmdlet modifies disk allocation for protected data in System Center 2016 - Data Protection Manager (DPM).

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

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

### -CalculateShrinkThresholds
Indicates that DPM calculates the thresholds to which the recovery point volume can decrease.

This parameter sets the properties **ShadowCopySizeAfterMaxShrink** and **ShadowCopySizeAfterMinShrink**.
When you use this parameter, the **Get-DiskAllocation** cmdlet returns two values.
To reduce the recovery point volume, specify a value between the two returned values to the *ShadowCopyArea* parameter of the **Set-DiskAllocation** cmdlet.
However, if you cannot reduce the recovery point volume, the cmdlet throws an exception with the appropriate error code.

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

### -CalculateSize
Indicates that DPM calculates the space allocated on a disk.

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

### -Datasource
Specifies a data source object for which this cmdlet modifies disk allocation.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrimaryDpmServer
Indicates that DPM recovers data to a DPM server.

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

### -Tag
Specifies a custom property that distinguishes the replies to each asynchronous call.
You can use parameter if you build a graphical user interface by using cmdlets.
Do not use this parameter if you work with the DPM Management Shell.

```yaml
Type: Object
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

## NOTES

## RELATED LINKS

[Edit-DPMDiskAllocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Edit-DPMDiskAllocation.md)

[Set-DPMDatasourceDiskAllocation](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceDiskAllocation.md)

