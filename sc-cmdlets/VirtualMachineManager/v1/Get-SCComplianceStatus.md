---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCComplianceStatus.md
schema: 2.0.0
ms.assetid: B16BC2EF-92BC-470D-8B0A-3EB3986C1274
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCComplianceStatus.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCComplianceStatus.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCComplianceStatus.md
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

[Set-SCComplianceStatus](xref:VirtualMachineManager/v1/Set-SCComplianceStatus.md)

[Start-SCComplianceScan](xref:VirtualMachineManager/v1/Start-SCComplianceScan.md)

[Get-SCVirtualDiskDrive](xref:VirtualMachineManager/v1/Get-SCVirtualDiskDrive.md)

