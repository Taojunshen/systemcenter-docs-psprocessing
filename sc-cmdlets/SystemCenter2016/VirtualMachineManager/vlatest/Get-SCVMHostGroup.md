---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 005B35E3-A897-4A58-A8A2-2D7606742011
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMHostGroup

## SYNOPSIS
Gets a host group object from the VMM database.

## SYNTAX

### Connection (Default)
```
Get-SCVMHostGroup [-VMMServer <ServerConnection>] [[-Name] <String>] [<CommonParameters>]
```

### ID
```
Get-SCVMHostGroup [-VMMServer <ServerConnection>] -ID <Guid> [[-Name] <String>] [<CommonParameters>]
```

### ParentHostGroup
```
Get-SCVMHostGroup -ParentHostGroup <HostGroup> [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostGroup** cmdlet gets one or more host group objects from the Virtual Machine Manager (VMM) database.

For more information about host groups, type `Get-Help New-VMHostGroup -Detailed`.

## EXAMPLES

### Example 1: Get all host groups at the specified path
```
PS C:\> Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup01" }
```

This command gets the host groups located at host path All Hosts\HostGroup01 and displays information about these host groups.

### Example 2: Display the name and path properties for all host groups
```
PS C:\> Get-SCVMHostGroup -VMMServer "VMMServer01.Contoso.com" | select -Property Name,Path
```

This command gets all host group objects from VMMServer01, selects the name and host group path properties, and displays those properties.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentHostGroup
Specifies the parent host group that contains one or more hosts, host groups, or host clusters.

```yaml
Type: HostGroup
Parameter Sets: ParentHostGroup
Aliases: ParentVMHostGroup

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
Parameter Sets: Connection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

```yaml
Type: ServerConnection
Parameter Sets: ID
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

[Move-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md)

[New-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostGroup.md)

[Remove-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md)

[Set-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md)

