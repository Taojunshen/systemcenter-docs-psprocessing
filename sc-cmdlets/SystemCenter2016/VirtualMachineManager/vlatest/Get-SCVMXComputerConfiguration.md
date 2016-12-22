---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B7BD4503-63B3-4B0D-A6DD-A383E2F7D2C9
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMXComputerConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMXComputerConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMXComputerConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMXComputerConfiguration

## SYNOPSIS
Gets VMX computer configuration objects from the VMM database that are associated with one or more VMware-based virtual machines.

## SYNTAX

```
Get-SCVMXComputerConfiguration [-VMMServer <ServerConnection>] [-VMXPath <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMXComputerConfiguration** cmdlet gets one or more VMX computer configuration objects from the Virtual Machine Manager (VMM) database that are associated with one or more VMware virtual machines.
Information about a virtual machine computer's hardware, disks, and operating system is stored in the VMX computer configuration object.

A VMX computer configuration object is used by the **New-SCV2V** cmdlet when it converts a VMware-based virtual machine deployed on an ESX host to a virtual machine deployed on a Windows-based Hyper-V host.

## EXAMPLES

### Example 1: Get all VMX computer configuration objects in your VMM environment
```
PS C:\> Get-SCVMXComputerConfiguration -VMMServer "VMMServer01.Contoso.com"
```

This command gets all VMX computer configuration objects from the VMM database and displays information about these VMX computer configuration objects to the user.

## PARAMETERS

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

### -VMXPath
Specifies the full UNC path to the .vmx file of a VMware virtual machine. 



Example format: `\\\\ServerName\VolumeName\DirectoryName\VMwareVM.vmx`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VMXMachineConfig
This cmdlet returns a **VMXMachineConfig** object.

## NOTES

## RELATED LINKS

[New-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md)

[Remove-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMXComputerConfiguration.md)

