---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F31D46C1-3909-4438-B481-64CD216541E3
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-PROTip

## SYNOPSIS
Adds a PRO tip.

## SYNTAX

### Server (Default)
```
Add-PROTip [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### VMSource
```
Add-PROTip [-VMMServer <ServerConnection>] -SourceVM <VM> -Name <String> [<CommonParameters>]
```

### HostSource
```
Add-PROTip [-VMMServer <ServerConnection>] -SourceHost <Host> -Name <String> [<CommonParameters>]
```

## DESCRIPTION
The **Add-PROTip** cmdlet adds a Performance and Resource Optimization (PRO) tip.
This cmdlet is only available in debug builds of PowerShell.

## EXAMPLES


## PARAMETERS

### -Name
Specifies the name of the PRO tip to add.

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

### -SourceHost
Specifies the source host.

```yaml
Type: Host
Parameter Sets: HostSource
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SourceVM
Specifies the host virtual machine.

```yaml
Type: VM
Parameter Sets: VMSource
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

[Clear-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md)

[Get-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md)

[Test-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md)

