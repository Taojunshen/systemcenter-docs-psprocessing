---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCApplicationDeployment.md
schema: 2.0.0
ms.assetid: F178B9E2-6EB1-4A05-8FAF-6EFA41014D80
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCApplicationDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCApplicationDeployment

## SYNOPSIS
Deletes an application deployment from an application profile.

## SYNTAX

```
Remove-SCApplicationDeployment [-ApplicationDeployment] <ApplicationDeployment> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCApplicationDeployment** cmdlet deletes an application deployment from an application profile.

## EXAMPLES

### Example 1: Remove all of the application deployments from an application profile
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile
PS C:\> $AppDeployment | Remove-SCApplicationDeployment
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets all spplication deployment objects for the application profile stored in $AppProfile and stores the objects in the $AppDeployment array.

The last command uses the pipeline operator to pass each of the objects stored in the $AppDeployment array to the **Remove-SCApplicationDeployment** cmdlet, which deletes the application deployment objects.

## PARAMETERS

### -ApplicationDeployment
Specifies an application deployment object.

```yaml
Type: ApplicationDeployment
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

## NOTES

## RELATED LINKS

[Add-SCApplicationDeployment](xref:VirtualMachineManager/v1/Add-SCApplicationDeployment.md)

[Get-SCApplicationDeployment](xref:VirtualMachineManager/v1/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:VirtualMachineManager/v1/Get-SCApplicationProfile.md)

[Set-SCApplicationDeployment](xref:VirtualMachineManager/v1/Set-SCApplicationDeployment.md)

