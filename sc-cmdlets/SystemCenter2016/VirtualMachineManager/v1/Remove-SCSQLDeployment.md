---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCSQLDeployment.md
schema: 2.0.0
ms.assetid: 698A4012-7F77-4535-A0DD-8D28DDD0E530
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCSQLDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSQLDeployment

## SYNOPSIS
Removes a SQL Server deployment from a SQL Server profile.

## SYNTAX

```
Remove-SCSQLDeployment [-SQLDeployment] <SQLDeployment> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSQLDeployment** cmdlet removes a Microsoft SQL Server deployment from a SQL Server profile.

## EXAMPLES

### Example 1: Remove a SQL Server deployment from a SQL profile
```
PS C:\>$SQLProfile = Get-SCSQLProfile -Name "SQLProfile01"
PS C:\> $SQLDeployment = Get-SCSQLDeployment -SQLProfile $SQLProfile -Name "SQL Deployment 01"
PS C:\> Remove-SCSQLDeployment -SQLDeployment $SQLDeployment
```

The first command gets the SQL Server profile object named SQLProfile01 and stores the object in the $SQLProfile variable.

The second command gets the SQL Server deployment object named SQL Deployment 01 from the SQL profile stored in $SQLProfile and then stores the object in the $SQLDeployment variable.

The last command removes the SQL Server deployment stored in $SQLDeployment from the SQL Server profile stored in $SQLProfile.

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

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -SQLDeployment
Specifies the SQL Server deployment that this cmdlet removes.

```yaml
Type: SQLDeployment
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

### SQLDeployment
This cmdlet returns a **SQLDeployment** object.

## NOTES

## RELATED LINKS

[Add-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCSQLDeployment.md)

[Get-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCSQLDeployment.md)

[Get-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCSQLProfile.md)

[Set-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCSQLDeployment.md)

