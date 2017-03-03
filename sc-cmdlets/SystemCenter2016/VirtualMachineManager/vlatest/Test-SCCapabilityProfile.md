---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 707CBB49-1813-4528-BC98-78ECA377C36E
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCCapabilityProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Test-SCCapabilityProfile

## SYNOPSIS
Validates the settings of a capability profile against a virtual machine, hardware profile, or virtual machine template.

## SYNTAX

### HardwareProfile
```
Test-SCCapabilityProfile -HardwareProfile <HardwareProfile> [-VMMServer <ServerConnection>]
 [-CapabilityProfile <CapabilityProfile>] [<CommonParameters>]
```

### VM
```
Test-SCCapabilityProfile -VM <VM> [-VMMServer <ServerConnection>] [-CapabilityProfile <CapabilityProfile>]
 [<CommonParameters>]
```

### Template
```
Test-SCCapabilityProfile -VMTemplate <Template> [-VMMServer <ServerConnection>]
 [-CapabilityProfile <CapabilityProfile>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCCapabilityProfile** cmdlet validates the settings of a capability profile against the virtual machine, hardware profile, or virtual machine template to which the profile is attached.

## EXAMPLES

### Example 1: Validate a capability profile for a virtual machine in a private cloud
```
PS C:\> $VM = Get-SCVirtualMachine -Name "CloudVM01"
PS C:\> $ProfileTest = Test-SCCapabilityProfile -VM $VM
PS C:\> $ProfileTest.ValidationErrors
```

The first command gets the virtual machine object named CloudVM01 and stores the object in the $VM variable.

The second command tests the settings of the capability profile attached to the virtual machine stored in $VM and stores the results in the $ProfileTest variable.

The last command displays any validation errors that occurred during testing.

## PARAMETERS

### -CapabilityProfile
Specifies a capability profile object.

```yaml
Type: CapabilityProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HardwareProfile
Specifies a hardware profile object.

```yaml
Type: HardwareProfile
Parameter Sets: HardwareProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VM
Aliases: 

Required: True
Position: Named
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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
Aliases: Template

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

[Get-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCCapabilityProfile.md)

[New-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCCapabilityProfile.md)

[Remove-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCCapabilityProfile.md)

[Set-SCCapabilityProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCCapabilityProfile.md)

