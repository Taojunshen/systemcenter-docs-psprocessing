---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Set-SCStorageFabric.md
schema: 2.0.0
ms.assetid: 3004D5A9-521B-49AD-A9FA-4C8969DAB80E
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageFabric.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageFabric.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Get-SCStorageFabric.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCStorageFabric

## SYNOPSIS
Gets a fibre channel fabric from the VMM database.

## SYNTAX

### All (Default)
```
Get-SCStorageFabric [-VMMServer <ServerConnection>] [[-Name] <String>] [-All] [<CommonParameters>]
```

### ID
```
Get-SCStorageFabric [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageFabric** cmdlet gets a Fibre Channel fabric from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get storage fabric by name
```
PS C:\>Get-SCStorageFabric -Name "Fabric01"
```

This command gets the storage fabric named Fabric01.

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
Specifies the unique ID foe the Fibre Channel fabric that this cmdlet gets.

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

### -Name
Specifies the name of the Fibre Channel fabric that this cmdlet gets.

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

### StorageFabric
This cmdlet returns a **StorageFabric** object.

## NOTES

## RELATED LINKS

[Set-SCStorageFabric](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCStorageFabric.md)
