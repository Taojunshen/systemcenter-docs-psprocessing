---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AA221F6D-9511-468E-99D6-24CD46B5B495
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobCategory.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobCategory.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJobCategory.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCDWJobCategory

## SYNOPSIS
Enables all data warehouse jobs within the specified category.

## SYNTAX

```
Enable-SCDWJobCategory [-JobCategoryName] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCDWJobCategory** cmdlet enables all data warehouse jobs within the specified category.

## EXAMPLES

### Example 1: Enable jobs by category
```
PS C:\>Enable-SCDWJobCategory -ComputerName "serverDW72" -JobCategoryName "CubeProcessing"
```

This command enables the jobs in the `CubeProssing` category.

### Example 2: Display job status
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" | Select-Object -Property CategoryName, IsEnabled -Unique | Format-Table -Property CategoryName, IsEnabled -AutoSize

CategoryName    IsEnabled

------------    ---------

Synchronization      True

CubeProcessing       True

Transform            True

Maintenance          True

Extract              True

Load                 True

Load                False
```

This command provides information about enabled and disabled jobs in the job categories.
If all the jobs in the category are enabled or disabled, the value in the **IsEnabled** column in the output reflects that value.
If at least one job in a job category has an opposite **IsEnabled** value from the other jobs in the same category, the job category name is repeated with that job's opposite **IsEnabled** value (as is the case for the `Load` category shown in the example output).
This is achieved by using the **Unique** parameter for the **Select-Object** command.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the **Credential** parameter must have access rights to the specified computer.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use when you are connecting to the server on which the System Center Data Access service is running.
The provided user account must have access to that server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCategoryName
Specifies the job category.
You can use the **Get-SCDWJob** cmdlet to retrieve job categories.
Valid job categories are Maintenance, Extract, Load, and Transform.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

