---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225414
schema: 2.0.0
ms.assetid: CD90BA97-4AF3-4A99-B153-726181379194
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMClassInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMClassInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Remove-SCSMClassInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCSMClassInstance

## SYNOPSIS
Removes a class instance.

## SYNTAX

```
Remove-SCSMClassInstance [-Instance] <EnterpriseManagementInstance[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMClassInstance** cmdlet permanently removes a class instance.

## EXAMPLES

### Example 1: Remove all class instances of a specific type
```
PS C:\>$Cmp = Get-SCSMClass -Name Microsoft.Windows.Computer
PS C:\>Get-SCSMClassInstance -Class $Cmp|Format-Table PrincipalName,DisplayName
PrincipalName                     DisplayName

-------------                     -----------

CenSupport.contoso.com            CenSupport$

Computer1.contoso.com             Computer1.contoso.com

WIN-752HJBSX24M.contoso.com



PS C:\>Get-SCSMClassInstance -Class $Cmp -Filter 'DisplayName -Like "C%"'
PrincipalName                     DisplayName

-------------                     -----------

Computer1.contoso.com             Computer1.contoso.com



PS C:\>Get-SCSMClassInstance -Class $Cmp -Filter 'DisplayName -like "Computer1%"' | Remove-SCSMClassInstance
PS C:\>Get-SCSMClassInstance -Class $Cmp|Format-Table PrincipalName,DisplayName
PrincipalName                     DisplayName

-------------                     -----------

CenSupport.contoso.com            CentSupport$

WIN-752HJBSX24M.woodgrove.com
```

These commands remove all class instances of type System.Windows.Computer when the instance class begins with the letter C.

## PARAMETERS

### -Instance
Specifies an instance of a configuration item object to be removed.

You can specify an **EnterpriseManagementObject** that is returned by the **Get-SCSMClassInstance** cmdlet.

```yaml
Type: EnterpriseManagementInstance[]
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

### Microsoft.EnterpriseManagement.Core.Cmdlets.Instances.EnterpriseManagementInstance
You can pipe a class instance to the *Instance* parameter of the **Remove-SCSMClassInstance** cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[New-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/New-SCSMClassInstance.md)

[Get-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMClassInstance.md)

[Update-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/Update-SCSMClassInstance.md)

