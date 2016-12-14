---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCComplianceStatus.md
schema: 2.0.0
ms.assetid: B16BC2EF-92BC-470D-8B0A-3EB3986C1274
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCComplianceStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCComplianceStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCComplianceStatus.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCComplianceStatus

## SYNOPSIS
Gets the compliance status of computers managed by VMM.

## SYNTAX

### All (Default)
```
Get-SCComplianceStatus [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### VMMManagedComputer
```
Get-SCComplianceStatus [-VMMServer <ServerConnection>] -VMMManagedComputer <VMMManagedComputer>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCComplianceStatus** cmdlet gets the compliance status object of one or more computers managed by Virtual Machine Manager (VMM).
The returned compliance status provides details on the compliance against assigned baselines.

## EXAMPLES

### Example 1: Get the compliance status of a host
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> $Compliance = Get-SCComplianceStatus -VMMManagedComputer $VMHost.ManagedComputer
PS C:\> $Compliance
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets the compliance status object for the host stored in $VMHost01 and stores the object in the $Compliance variable.

The last command displays information about the compliance status of VMHost01 to the user.

## PARAMETERS

### -All
Indicates that this cmdlet gets all subordinate objects independent of the parent object.
For example, the command `Get-SCVirtualDiskDrive -All` gets all virtual disk drive objects regardless of the virtual machine object or template object that each virtual disk drive object is associated with.

```yaml
Type: SwitchParameter
Parameter Sets: All
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMManagedComputer
Specifies a computer object that is managed by VMM.

```yaml
Type: VMMManagedComputer
Parameter Sets: VMMManagedComputer
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ComplianceStatus
This cmdlet returns a **ComplianceStatus** object.

## NOTES

## RELATED LINKS

[Set-SCComplianceStatus](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCComplianceStatus.md)

[Start-SCComplianceScan](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCComplianceScan.md)

[Get-SCVirtualDiskDrive](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md)

