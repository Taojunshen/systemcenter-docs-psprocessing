---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=246257
schema: 2.0.0
ms.assetid: 32406117-8068-4744-8E31-23FECA03F95F
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMRelationshipInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMRelationshipInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMRelationshipInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMRelationshipInstance

## SYNOPSIS
Removes an instance of a relationship.

## SYNTAX

```
Remove-SCSMRelationshipInstance [-Instance] <EnterpriseManagementRelationshipObject`1[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMRelationshipInstance** cmdlet removes an instance of a relationship.

## EXAMPLES

### Example 1: Remove a relationship instance
```
PS C:\>Get-SCSMRelationshipInstance â€"Id "2e5f43fc-31fa-e4f1-57d8-ec3c37bb2ba0" | Remove-SCSMRelationshipInstance
```

This command removes a relationship instance.

## PARAMETERS

### -Instance
Specifies the instance of relationship to be removed.

```yaml
Type: EnterpriseManagementRelationshipObject`1[]
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

### Microsoft.EnterpriseManagement.Common.EnterpriseManagementRelationshipObject
You can pipe a relationship instance to the *Instance* parameter of the **Remove-SCSMRelationshipInstance** cmdlet.

## OUTPUTS

### None.

## NOTES

## RELATED LINKS

[Get-SCSMRelationshipInstance](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMRelationshipInstance.md)

