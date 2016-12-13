---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCVMHostNetworkAdapterProfile.md
schema: 2.0.0
ms.assetid: BB55C94F-2AC1-473B-925D-8EA7AA31BC1A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostNetworkAdapterProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostNetworkAdapterProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostNetworkAdapterProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHostNetworkAdapterProfile

## SYNOPSIS
Gets a host network adapter profile.

## SYNTAX

### All
```
Get-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCVMHostNetworkAdapterProfile [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostNetworkAdapterProfile** cmdlet gets a host network adapter profile by its ID.

## EXAMPLES

### Example 1: Get a host network adapter profile by its ID
```
PS C:\>Get-SCVMHostNetworkAdapterProfile -ID "259f47c7-c5a9-429d-a421-d232f9b34991"
```

This command gets the network adapter profile object with the ID of 259f47c7-c5a9-429d-a421-d232f9b34991.

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

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### HostNetworkAdapterProfile[]
This cmdlet returns an array of **HostNetworkAdapterProfile** objects.

## NOTES

## RELATED LINKS

[New-SCVMHostNetworkAdapterProfile](xref:VirtualMachineManager/v1/New-SCVMHostNetworkAdapterProfile.md)

[Remove-SCVMHostNetworkAdapterProfile](xref:VirtualMachineManager/v1/Remove-SCVMHostNetworkAdapterProfile.md)

