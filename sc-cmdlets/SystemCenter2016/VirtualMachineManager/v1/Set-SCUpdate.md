---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCUpdate.md
schema: 2.0.0
ms.assetid: F0755C6D-7C5B-4B20-83F9-7DF709D67E6B
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCUpdate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCUpdate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCUpdate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCUpdate

## SYNOPSIS
Accepts Microsoft Software License Terms for software updates that require acceptance.

## SYNTAX

### Default (Default)
```
Set-SCUpdate [-VMMServer <ServerConnection>] [-Update] <SoftwareUpdate> [-AcceptLicenseAgreement]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### UIOnlyEULAAcceptance
```
Set-SCUpdate [-VMMServer <ServerConnection>] [-Update] <SoftwareUpdate> [-AcceptLicenseAgreement]
 -ClientID <Guid> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCUpdate** cmdlet is used to accept Microsoft Software License Terms for updates that require acceptance.

## EXAMPLES

### Example 1: Accept the license agreement for an update
```
PS C:\>$Update = Get-SCUpdate -KBArticle "948465"
PS C:\> Set-SCUpdate -Update $Update -AcceptLicenseAgreement
```

The first command gets the update for KB article 948465 and stores the object in the $Update variable.

The second command displays the license agreement text for the update stored in $Update and prompts whether to accept or decline it.

## PARAMETERS

### -AcceptLicenseAgreement
Indicates that the Microsoft Software License Terms for a software update are accepted.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientID
For internal use only (not for use in your code).

```yaml
Type: Guid
Parameter Sets: UIOnlyEULAAcceptance
Aliases: 

Required: True
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

### -Update
Specifies a software update object.

```yaml
Type: SoftwareUpdate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Update
This cmdlet returns an **Update** object.

## NOTES

## RELATED LINKS

[Get-SCUpdate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCUpdate.md)

