---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCodeIntegrityPolicy.md
schema: 2.0.0
ms.assetid: E45BD2C4-97B7-490A-9DBC-1C084B469940
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCCodeIntegrityPolicy.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCCodeIntegrityPolicy.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCCodeIntegrityPolicy.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCCodeIntegrityPolicy

## SYNOPSIS
Modifies a code integrity policy.

## SYNTAX

```
Set-SCCodeIntegrityPolicy -CodeIntegrityPolicy <CodeIntegrityPolicy> [-Name <String>] [-Path <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCCodeIntegrityPolicy** cmdlet modifies a code integrity policy in Virtual Machine Manager (VMM).

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -CodeIntegrityPolicy
Specifies the code integrity policy to modify.

```yaml
Type: CodeIntegrityPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
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

### -Name
Specifies the name of the code integrity policy to modify.

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

### -Path
Specifies the destination path for the operation. 



Example formats: 

 Local path:       `-Path "F:\"`

 UNC path:         `-Path "\\\\Library\Templates"`

 Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

 VMware ESX path:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`

 Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/Get-SCCodeIntegrityPolicy.md)

[New-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/New-SCCodeIntegrityPolicy.md)

[Remove-SCCodeIntegrityPolicy](xref:VirtualMachineManager/v1/Remove-SCCodeIntegrityPolicy.md)

