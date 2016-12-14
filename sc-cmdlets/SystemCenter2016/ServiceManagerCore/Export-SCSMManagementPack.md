---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225398
schema: 2.0.0
ms.assetid: CDED78E0-B2EA-4D9D-B380-B608BFA8D691
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Export-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Export-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Export-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Export-SCSMManagementPack

## SYNOPSIS
Exports a management pack as an XML file for import into Service Manager.

## SYNTAX

```
Export-SCSMManagementPack [-ManagementPack] <ManagementPack[]> [-PassThru] -Path <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Export-SCSMManagementPack** cmdlet exports a management pack as an unsealed, valid XML formatted file that you can later import into smshort.
All of the management packâ€™s information is included in the file as XML data.
You can use this cmdlet to save or archive management pack information.

## EXAMPLES

### Example 1: Export management packs matching a name
```
PS C:\>Get-SCSMManagementPack -Name "*snmp*"| Export-SCSMManagementPack â€"Path "C:\temp;ls C:\temp\*snmp*"
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a---         10/2/2008  11:37 AM     240010 System.Snmp.Library.xml
```

This command exports all management packs with a name that is similar to snmp.

## PARAMETERS

### -ManagementPack
Specifies one or more management packs to export.
You can obtain a **ManagementPack** object that is returned by the **Get-SCManagementPack** cmdlet.

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

### -PassThru
Specifies that output of this cmdlet can be passed to other cmdlets.

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

### -Path
Specifies the folder into which exported management pack files will be stored.
The specified folder must exist before you run the cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
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

### Microsoft.EnterpiseManagement.Configuration.ManagementPack
You can pipe a management pack to the *ManagementPack* parameter of the **Export-SCSMManagementPack** cmdlet, for example, the object that is returned by the **Get-SCSMManagementPack** cmdlet.

## OUTPUTS

### Microsoft.EnterpiseManagement.Configuration.ManagementPack
When you use the *PassThru* parameter, the **Export-SCSMManagementPack** cmdlet returns a **ManagementPack** object.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Import-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Protect-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Test-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/New-SCSMManagementPackBundle.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Remove-SCSMManagementPack.md)

