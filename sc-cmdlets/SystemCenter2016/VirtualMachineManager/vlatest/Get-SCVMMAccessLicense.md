---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Register-SCVMMAccessLicense.md
schema: 2.0.0
ms.assetid: 886AC6ED-70D6-4866-8634-44FBD442A857
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMAccessLicense.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMAccessLicense.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMAccessLicense.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMMAccessLicense

## SYNOPSIS
Gets the VMM server license information.

## SYNTAX

### License
```
Get-SCVMMAccessLicense -VMMServer <ServerConnection> [-License] [<CommonParameters>]
```

### LicenseBy
```
Get-SCVMMAccessLicense -VMMServer <ServerConnection> -LicenseBy <LicenseBy> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMMAccessLicense** cmdlet gets the Virtual Machine Manager (VMM) server license information.

## EXAMPLES

### Example 1: Get a list of available licenses for VMM
```
PS C:\>Get-SCVMMAccessLicense -VMMServer "VMMServer01.Contoso.com" -License
```

This command returns a list of available licenses for the VMM server VMMServer01.

### Example 2: Get all licenses that have a LicenseBy value of "ManagementServer"
```
PS C:\>Get-SCVMMAccessLicense -VMMServer "VMMServer01.Contoso.com" -LicenseBy "ManagementServer"
```

This command gets all management server licenses on VMM server VMMServer01.

### Example 3: Get all licenses that have a LicenseBy value of "SML"
```
PS C:\>Get-SCVMMAccessLicense -VMMServer "VMMServer01.Contoso.com" -LicenseBy "SML"
```

This command returns a list of licensed hosts associated with VMM server VMMServer01.

### Example 4: Get all licenses that have a LicenseBy value of "VOSE"
```
PS C:\>Get-SCVMMAccessLicense -VMMServer "VMMServer01.Contoso.com" -LicenseBy "VOSE"
```

This command returns a list of licensed virtual machines associated with VMM server VMMServer01.

## PARAMETERS

### -License
Indicates that all available licenses are returned.

```yaml
Type: SwitchParameter
Parameter Sets: License
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseBy
Specifies how VMM is licensed.
The acceptable values for this parameter are:

- SML
- ManagementServer
- VOSE

```yaml
Type: LicenseBy
Parameter Sets: LicenseBy
Aliases: 
Accepted values: SML, ManagementServer, VOSE

Required: True
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

Required: True
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

[Register-SCVMMAccessLicense](xref:SystemCenter2016/VirtualMachineManager/vlatest/Register-SCVMMAccessLicense.md)

