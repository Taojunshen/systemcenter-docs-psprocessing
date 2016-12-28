---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 82EACE45-887B-478F-8984-32ABAC7FB57D
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobCategory.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobCategory.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJobCategory.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCDWJobCategory

## SYNOPSIS
Disables all jobs within a job category.

## SYNTAX

```
Disable-SCDWJobCategory [-JobCategoryName] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCDWJobCategory** cmdlet disables all jobs within a job category.

## EXAMPLES

### Example 1: Disable jobs by category
```
PS C:\>Disable-SCDWJobCategory -ComputerName "serverDW72" -JobCategoryName "CubeProcessing"
```

This command disables the jobs in the `CubeProssing` category.

### Example 2: Disable jobs using credentials
```
PS C:\>$credUser = Get-Credential
PS C:\>Disable-SCDWJobCategory -ComputerName "serverDW72" -JobCategoryName "CubeProcessing" â€"Credential $credUser
```

The first command stores user credentials for the *Credential* parameter.

The second command disables the jobs in the `CubeProssing` category using the specified credentials.

### Example 3: Display job enabled/disabled status
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" | Select-Object -Property CategoryName, IsEnabled -Unique | Format-Table -Property CategoryName, IsEnabled -AutoSize
```

This command provides information about enabled and disabled jobs in the job categories.
If all the jobs in the category are either enabled or disabled, the value in the **IsEnabled** column in the output reflects that value.

If at least one job in a job category has an opposite **IsEnabled** value from the other jobs in the same category, the job category name is repeated with that value (as is the case for the `Load` category in the example output).
This is achieved by using the **Unique** parameter with the **Select-Object** command.

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
The user account that is provided must have access to that server.

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
Specifies the name of the job category.
You can use the **Get-SCDWJob** cmdlet to retrieve this value.
Examples of valid job categories are Maintenance, Extract, Load, and Transform.

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

