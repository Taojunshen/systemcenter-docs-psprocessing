---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCISO.md
schema: 2.0.0
ms.assetid: 7E3D0141-E1AF-4146-9394-06CC12D1CFAF
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCISO.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCISO.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-SCISO.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCISO

## SYNOPSIS
Removes an ISO file from the VMM library.

## SYNTAX

```
Remove-SCISO [-ISO] <ISO> [-Force] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCISO** cmdlet removes an ISO file from the Virtual Machine Manager (VMM) library and deletes the ISO file on the library server.

If the ISO is attached to a virtual machine, template, or hardware profile, and if you do not specify the *Force* parameter, VMM lists the container that includes the ISO and prompts you to confirm that you want to remove the ISO: 



- If you reply Yes, VMM removes the association between the ISO and the container to which it is attached, and then deletes the ISO object from VMM. 


- If you reply No, the operation is cancelled.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove an ISO object and delete the corresponding .iso file
```
PS C:\>$ISO = Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "OsISO.iso" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Remove-SCISO -ISO $ISO
```

The first command gets the ISO object named OsISO.iso from LibraryServer01 and stores the ISO object in the $ISO variable.

The second command removes the ISO object from the library and deletes the corresponding .iso file from the file system on the library server.

### Example 2: Remove multiple ISO objects from the library
```
PS C:\>$ISOs = Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "OsISO" }
PS C:\> $ISOs | Remove-SCISO
```

The first command gets all ISO objects whose name includes the string "OsISO" and stores these ISO objects in the $ISOs variable.

The second command passes each ISO object in $ISOs to the **Remove-SCISO** cmdlet, which removes each ISO object from the library and deletes the corresponding .iso file from the file system on the library server.

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

### -ISO
Specifies an ISO object.

```yaml
Type: ISO
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
* Requires a VMM ISO object, which can be retrieved by using the Get-SCISO cmdlet.

## RELATED LINKS

[Get-SCISO](xref:VirtualMachineManager/v1/Get-SCISO.md)

[Set-SCISO](xref:VirtualMachineManager/v1/Set-SCISO.md)

