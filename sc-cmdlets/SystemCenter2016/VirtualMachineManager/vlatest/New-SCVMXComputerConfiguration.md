---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5D1397AB-F265-4BF5-8445-77D60FB220DA
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMXComputerConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCVMXComputerConfiguration

## SYNOPSIS
Creates a VMX computer configuration object by gathering virtual machine configuration information from a virtual machine created in VMware that you plan to convert to a virtual machine deployed on a Windows-based host managed by VMM.

## SYNTAX

```
New-SCVMXComputerConfiguration [-VMMServer <ServerConnection>] [-VMXPath] <String>
 [-LibraryServer <LibraryServer>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMXComputerConfiguration** cmdlet creates a VMX computer configuration object by gathering information about the physical characteristics of a VMware-based virtual machine and its disks that you plan to convert to a virtual machine deployed on a Windows-based Hyper-V host managed by Virtual Machine Manager (VMM).
This cmdlet does not collect information about the operating system or data on the VMware-based virtual machine.

VMWare virtual hard disk formats supported by the **New-SCVMXComputerConfiguration** cmdlet include: 

 - monolithicSparse

 - monolithicFlat

 - vmfs

 - twoGbMaxExtentSparse

 - twoGbMaxExtentFlat

## EXAMPLES

### Example 1: Gather information from a VMware-based virtual machine
```
PS C:\> $LibServ = Get-SCLibraryServer -ComputerName "LibServer01.Contoso.com"
PS C:\> New-SCVMXComputerConfiguration -LibraryServer $LibServ -VMXPath "\\FileServer01\MSSCVMMLibrary\VMware\VMSource.vmx"
```

The first command gets the library server object named LibServer01 in the Contoso.com domain and stores the object in the $LibServ variable.

The last command gathers the machine configuration information for the .vmx file located at "\\FileServer01\MSSCVMMLibrary\VMware\VMSource.vmx" on the library server.
The **New-SCVMXComputerConfiguration** cmdlet stores the resulting VMX computer configuration object associated with VMSource.vmx in the VMM database.

Note: If you look in Library view in the VMM console, you cannot see the file VMSource.vmx file because the .vmx file is part of a single virtual machine object.
What you see in Library view is the virtual machine.
To find the path to a .vmdk file, view the properties for that virtual machine.

## PARAMETERS

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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
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

### -VMXPath
Specifies the full UNC path to the .vmx file of a VMware virtual machine. 



Example format:  `\\ServerName\VolumeName\DirectoryName\VMwareVM.vmx`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Get-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMXComputerConfiguration.md)

[Remove-SCVMXComputerConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMXComputerConfiguration.md)

