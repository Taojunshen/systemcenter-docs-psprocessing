---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 13198FB5-F0A6-466B-85F5-6646F24B5C83
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScript.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScript.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScript.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCScript

## SYNOPSIS
Removes a script object from VMM.

## SYNTAX

```
Remove-SCScript [-Script] <Script> [-Force] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCScript** cmdlet removes one or more script objects from the VMM library and deletes the corresponding script file on the library server.

If the script is attached to a template or hardware profile (and if you do not use the *Force* parameter), Virtual Machine Manager (VMM) lists the container that contains the script and prompts you to confirm that you want to remove the script:

- If you reply Yes, VMM removes the association between the script and the container to which it is attached, and then deletes the script object from VMM.
- If you reply No, the operation is cancelled.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a script object and delete the corresponding script file
```
PS C:\> $Scripts = @(Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AddHost.ps1"} )
PS C:\> $Scripts.Count
PS C:\> $Scripts | select Name,SharePath | Format-List
PS C:\> Remove-SCScript -Script $Scripts[0] -Force
```

The first command gets the script object named AddHost.ps1 from the VMM library on VMMServer01 and stores the object in the array named $Scripts.
More than one file with the same name might exist if more than one container for scripts exists on the specified library server.

The second command counts the number of scripts in $Scrips and displays the results to the user.

The third command passes each script object in $Scripts to the Select-Object cmdlet, which selects the name and share path for each script in the array.
The command then passes these results to the Format-List cmdlet to display each script name, and its share path, to the user.

The last command deletes the first object in the $Scripts array and uses the *Force* parameter to ensure that the script object is removed from the VMM database and the corresponding script file is deleted from the file system on the library server.

### Example 2: Remove multiple scripts from the library
```
PS C:\> $Scripts = Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "Sysprep" }
PS C:\> $Scripts | Remove-SCScript -Confirm
```

The first command gets all script objects whose names include the string "Sysprep" from VMMServer01 and then stores these objects in the array named $Scripts.

The second command passes each script object in $Scripts to **Remove-SCScript**, which removes each script object from the library and deletes each corresponding script file from the file system on the library server.

The *Confirm* parameter prompts you to confirm that you do want to remove these scripts.
You have the option to confirm the deletion of all scripts at once or to confirm the deletion of each script one-by-one.

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

### -Script
Specifies a VMM script object.

```yaml
Type: Script
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

[Get-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md)

[Set-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScript.md)

