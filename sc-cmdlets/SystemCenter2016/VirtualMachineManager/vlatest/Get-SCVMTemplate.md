---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 93D695A4-AACC-4159-8988-B8CC07240BFC
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMTemplate

## SYNOPSIS
Gets virtual machine template objects from the VMM library.

## SYNTAX

### All (Default)
```
Get-SCVMTemplate [-VMMServer <ServerConnection>] [-ComputerTierTemplate <ComputerTierTemplate>] [-All]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Name
```
Get-SCVMTemplate [-VMMServer <ServerConnection>] [-ComputerTierTemplate <ComputerTierTemplate>]
 [[-Name] <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ID
```
Get-SCVMTemplate [-VMMServer <ServerConnection>] [-ComputerTierTemplate <ComputerTierTemplate>] [-ID <Guid>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMTemplate** cmdlet gets virtual machine template objects from the Virtual Machine Manager (VMM) library.

For information about how virtual machine templates are used to create new virtual machines, type `Get-Help New-Template -Detailed`.

## EXAMPLES

### Example 1: Get all templates stored in the library
```
PS C:\> Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com"
```

This command gets all template objects from the VMM library on VMMServer01, and then displays information about these templates.

### Example 2: Get all templates stored in the library that have a similar name
```
PS C:\> Get-SCVMTemplate -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -like "Windows Server 2008*" }
```

This command gets all template objects from the VMM library on VMMServer01 whose name begins with "Windows Server 2008," and then displays information about these templates.

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

### -ComputerTierTemplate
Specifies a computer tier template object.

```yaml
Type: ComputerTierTemplate
Parameter Sets: (All)
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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Template
This cmdlet returns a **Template** object.

## NOTES

## RELATED LINKS

[New-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMTemplate.md)

[Remove-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMTemplate.md)

[Set-SCVMTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMTemplate.md)

