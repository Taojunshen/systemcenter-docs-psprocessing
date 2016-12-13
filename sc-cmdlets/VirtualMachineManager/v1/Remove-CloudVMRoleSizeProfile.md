---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-CloudVMRoleSizeProfile.md
schema: 2.0.0
ms.assetid: 7AF4FCD2-74CB-46F9-B168-3FA114A4106E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-CloudVMRoleSizeProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-CloudVMRoleSizeProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Remove-CloudVMRoleSizeProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-CloudVMRoleSizeProfile

## SYNOPSIS
Removes a cloud virtual machine role size profile.

## SYNTAX

```
Remove-CloudVMRoleSizeProfile [-CloudVmRoleSizeProfile] <CloudVmRoleSizeProfile>
 [-VMMServer <ServerConnection>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-CloudVMRoleSizeProfile** cmdlet removes a cloud virtual machine role size profile.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -CloudVmRoleSizeProfile
Specifies a cloud virtual machine role size profile object.

```yaml
Type: CloudVmRoleSizeProfile
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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-CloudVMRoleSizeProfile](xref:VirtualMachineManager/v1/Get-CloudVMRoleSizeProfile.md)

[New-CloudVMRoleSizeProfile](xref:VirtualMachineManager/v1/New-CloudVMRoleSizeProfile.md)

[Set-CloudVMRoleSizeProfile](xref:VirtualMachineManager/v1/Set-CloudVMRoleSizeProfile.md)

