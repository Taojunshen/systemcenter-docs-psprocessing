---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225413
schema: 2.0.0
ms.assetid: 717FF616-D2C5-4ECC-951A-94CFDB45BE24
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Protect-SCSMManagementPack

## SYNOPSIS
Protects a management pack to prevent modification.

## SYNTAX

### FromManagementPack
```
Protect-SCSMManagementPack [-ManagementPack] <ManagementPack[]> -OutputDirectory <String> -KeyFilePath <String>
 -CompanyName <String> [-Copyright <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPackFile
```
Protect-SCSMManagementPack [-ManagementPackFile] <String[]> -OutputDirectory <String> -KeyFilePath <String>
 -CompanyName <String> [-Copyright <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Protect-SCSMManagementPack** cmdlet seals a management pack to prevent modification.
The sealed management pack is stored in the folder that is specified by the *OutputDirectory* parameter.
The sealed management pack can be imported into smshort.

## EXAMPLES

### Example 1: Seal a management pack
```
PS C:\>$Mp = Get-SCSMManagementPack -ManagementPackFile "Resources\ContosoForm.xml"
PS C:\> $Arguments = @{
>> ManagementPack = $Mp
>> OutputDirectory = $PWD
>> KeyFilePath = "Resources\keyfile.snk"
>> CompanyName = "Contoso"
>> Copyright = "2011"}
PS C:\> Protect-SCSMManagementPack @Arguments
```

These commands seal the management pack ContosoForm.xml.

## PARAMETERS

### -CompanyName
Specifies the company name for the signature of the sealed management pack.

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

### -Copyright
Specifies the copyright string for the signature of the sealed management pack.

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

### -KeyFilePath
Specifies the path to the file that contains the key for the signature of the sealed management pack.

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

### -ManagementPack
Specifies the management pack to seal.
You can enter a **ManagementPack** object that is returned by the **Get-SCSMManagementPack** cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPackFile
Specifies the name of the management pack file.

```yaml
Type: String[]
Parameter Sets: FromManagementPackFile
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OutputDirectory
Specifies the folder for the sealed management pack.

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

### -PassThru
Specifies the output object that represents the sealed management pack.
This output object can be passed to other cmdlets.

```yaml
Type: SwitchParameter
Parameter Sets: FromManagementPack
Aliases: 

Required: False
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

### System.String
You can pipe a management pack file name to the *ManagementPackFIle* parameter of the `Protect-SCSMManagementPack` cmdlet.

### Microsoft.EnterpriseManagement.Configuration.ManagementPackManagement pack object.
You can pipe a management pack object to the *ManagementPack* parameter of the **Protect-SCSMManagementPack** cmdlet, for example, the object that is returned by the **Get-SCSMManagementPack** cmdlet.

## OUTPUTS

### Management pack object.
This cmdlet generates a management pack object when it is used with the *PassThru* parameter.

### Sealed management pack.
This cmdlet generates a sealed management pack that is stored in the folder that is specified by the *OutputDirectory* parameter.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Import-SCSMManagementPack.md)

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Export-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementPack.md)

