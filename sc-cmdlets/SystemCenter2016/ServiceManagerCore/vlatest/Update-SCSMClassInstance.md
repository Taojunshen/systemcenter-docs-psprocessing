---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7845DC60-CB96-4564-8F6A-95C314E67664
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMClassInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMClassInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMClassInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Update-SCSMClassInstance

## SYNOPSIS
Updates property values of a class instance.

## SYNTAX

```
Update-SCSMClassInstance [-Instance] <EnterpriseManagementInstance[]> [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMClassInstance** cmdlet updates property values of a class instance.

## EXAMPLES

### Example 1: Mark class instances for deletion
```
PS C:\>Get-SCSMClassInstance (Get-SCSMClass â€"Name "System.Printer") | %{ $_.ObjectStatus = â€pending deleteâ€ ; $_ } | Update-SCSMClassinstance
```

This command updates all configuration item instances of class System.Printer to mark them for deletion.

### Example 2: Change the location value of a Service Manager configuration item instance
```
PS C:\>Get-SCSMClassInstance -Class (Get-SCSMClass -Name "Microsoft.Ad.Printer") -Filter 'Location -eq "Seattle"' | Format-Table UNCName,PrinterName,Description,Location
UNCName                PrinterName Description Location
-------                ----------- ----------- --------
\\PrintServer\Printer4 Printer4                Seattle
\\PrintServer\Printer7 Printer7                Seattle
\\PrintServer\Printer1 Printer1                Seattle
\\PrintServer\Printer9 Printer9                Seattle
\\PrintServer\Printer6 Printer6                Seattle
\\PrintServer\Printer3 Printer3                Seattle
\\PrintServer\Printer2 Printer2                Seattle
\\PrintServer\Printer5 Printer5                Seattle
\\PrintServer\Printer0 Printer0                Seattle
\\PrintServer\Printer8 Printer8                Seattle


PS C:\>Get-SCSMClassInstance -Class (Get-SCSMClass "Microsoft.Ad.Printer") -Filter 'Location -eq "Seattle"'| %{ $_.Location = "Portland"; $_ } | Update-SCSMInstance Get-SCSMObject -ClassName "Microsoft.Ad.Printer"
UNCName                PrinterName Description Location
-------                ----------- ----------- --------
\\PrintServer\Printer4 Printer4                Portland
\\PrintServer\Printer7 Printer7                Portland
\\PrintServer\Printer1 Printer1                Portland
\\PrintServer\Printer9 Printer9                Portland
\\PrintServer\Printer6 Printer6                Portland
\\PrintServer\Printer3 Printer3                Portland
\\PrintServer\Printer2 Printer2                Portland
\\PrintServer\Printer5 Printer5                Portland
\\PrintServer\Printer0 Printer0                Portland
\\PrintServer\Printer8 Printer8                Portland
```

This commands changes the location value of a Service Manager configuration item instance.

## PARAMETERS

### -Instance
Specifies an instance of a class to update.

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

### -PassThru
Indicates that the class instance is returned to the current Windows PowerShell session after the update is complete.
This output object can then be passed to other cmdlets.

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
You can pipe a class instance to the *Instance* parameter of the **Update-SCSMClassInstance** cmdlet.

## OUTPUTS

### EnterpriseManagementInstance
This cmdlet generates an EnterpriseManagementInstance object when the `PassThru` parameter is used.

## NOTES

## RELATED LINKS

[New-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMClassInstance.md)

[Remove-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMClassInstance.md)

[Get-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClassInstance.md)

