---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 00A66716-8B86-4307-8F6E-A6369D8475C3
updated_at: 12/22/2016 3:49 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-CloudVMRoleSizeProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-CloudVMRoleSizeProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/8c8c20cafa5c1354636ca569508504b8373fce2c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-CloudVMRoleSizeProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-CloudVMRoleSizeProfile

## SYNOPSIS
Updates a cloud VM role size profile.

## SYNTAX

```
Set-CloudVMRoleSizeProfile [-Description <String>] [-CPUCount <UInt32>] [-MemoryMB <UInt32>]
 [-HWProfileId <Guid>] [-VMMServer <ServerConnection>] [-VMRoleSizeProfile] <CloudVmRoleSizeProfile>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-CloudVMRoleSizeProfile** cmdlet updates a cloud VM role size profile.

## EXAMPLES


## PARAMETERS

### -CPUCount
Specifies the number of CPUs on a virtual machine, on a hardware profile, or on a template.
Types of hosts support the following number of CPUs: 

- Hyper-V.
Up to four CPUs per virtual machine, depending on guest operating system.
- VMware ESX.
Up to four CPUs per virtual machine, but only one CPU on a virtual machine that runs Windows NT 4.0. 
- Citrix XenServer.
Up to eight CPUs per virtual machine, depending on guest operating system.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
States a description for the specified object.

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

### -HWProfileId


```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -MemoryMB
Specifies the amount of memory in megabytes (MB) for a user role quota or cloud capacity.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -VMRoleSizeProfile
Specifies a cloud VM role size profile object.

To obtain a cloud VM role size profile object, use the **Get-CloudVMRoleSizeProfile** cmdlet.

```yaml
Type: CloudVmRoleSizeProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-CloudVMRoleSizeProfile.md)

[New-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-CloudVMRoleSizeProfile.md)

[Remove-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-CloudVMRoleSizeProfile.md)

