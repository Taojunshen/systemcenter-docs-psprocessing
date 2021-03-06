---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DE25C3C8-B564-4FB9-970D-9C226780FDB1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabricClassification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabricClassification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabricClassification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCStorageFabricClassification

## SYNOPSIS
Gets Fibre Channel fabric classification objects.

## SYNTAX

### All (Default)
```
Get-SCStorageFabricClassification [-VMMServer <ServerConnection>] [[-Name] <String>] [-All]
 [<CommonParameters>]
```

### ID
```
Get-SCStorageFabricClassification [-VMMServer <ServerConnection>] [[-Name] <String>] [-ID <Guid>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCStorageFabricClassification** cmdlet gets Fibre Channel classification objects.

## EXAMPLES

### Example 1: Get a storage fabric classification by name
```
PS C:\> Get-SCStorageFabricClassification -Name "PROD"
```

This command gets the storage fabric classification named PROD.

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
Specifies the unique ID of the Fibre Channel fabric classification that this cmdlet gets.

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
Specifies the name of the Fibre Channel fabric classification that this cmdlet gets.

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

### StorageFabricClassification
This cmdlet returns a **StorageFabricClassification** object.

## NOTES

## RELATED LINKS

[New-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageFabricClassification.md)

[Remove-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageFabricClassification.md)

[Set-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabricClassification.md)

