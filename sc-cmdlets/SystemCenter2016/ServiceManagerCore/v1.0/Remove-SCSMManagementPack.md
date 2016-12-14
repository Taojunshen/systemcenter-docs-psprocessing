---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225416
schema: 2.0.0
ms.assetid: 4EFC57E6-92A3-44A8-96E8-0649F4CE2C1A
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/v1.0/Remove-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMManagementPack

## SYNOPSIS
Removes management packs.

## SYNTAX

```
Remove-SCSMManagementPack [-ManagementPack] <ManagementPack[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMManagementPack** cmdlet removes management packs, along with all instances of types that are included in those management packs.
You cannot remove a management pack when it is depended on by other management packs.

## EXAMPLES

### Example 1: Remove management packs by name by using the pipeline operator
```
PS C:\>Get-SCSMManagementPack | Where{ $_.Name -Match "Contoso" } | Remove-SCSMManagementPack
```

This command removes all management packs in which the name matches the string "Contoso." The name is passed to the command by using the pipeline operator.

### Example 2 : Remove management packs by name without using the pipeline operator
```
PS C:\>$Mps = Get-SCSMManagementPack | Where{ $_.Name -Match "Contoso" }; Remove-SCSMManagementPack $Mps
```

This command removes all management packs in which the name matches the string "Contoso."

## PARAMETERS

### -ManagementPack
Specifies the management pack to remove.
You can specify a **ManagementPack** object that is returned by the **Get-SCSMManagementPack** cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
You can pipe a management pack to the *ManagementPack* parameter of the **Remove-SCSMManagementPack** cmdlet, for example, the object that is returned by the **Get-SCSMManagementPack** cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/Import-SCSMManagementPack.md)

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/Export-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/Protect-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/v1.0/Test-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/v1.0/New-SCSMManagementPackBundle.md)

