---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D7D88DE1-5A6C-44DE-A3D4-AB88F01F6741
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryRating.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryRating.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryRating.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCLibraryRating

## SYNOPSIS
Calculates the placement rating of library servers to determine whether a SAN transfer can be used to transfer a virtual machine from a host to the library.

## SYNTAX

```
Get-SCLibraryRating -LibraryServer <LibraryServer[]> [-VMMServer <ServerConnection>] [-VM <VM>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLIbraryRating** cmdlet calculates the placement rating of library servers managed by Virtual Machine Manager (VMM).
Specifically, this rating indicates whether VMM can use SAN transfer to transfer a particular virtual machine from a host server to a library server.
If a SAN transfer is not possible, you can use a LAN transfer to store the virtual machine in the library.

For information about how to store a virtual machine in the VMM library, type `Get-Help Save-SCVirtualMachine -Detailed`.

## EXAMPLES

### Example 1: Determine whether you can use a SAN transfer to store a virtual machine on the specified library server
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $LibServer = Get-SCLibraryServer -ComputerName "LibraryServer01.Contoso.com" 
PS C:\> $LibRating = Get-SCLibraryRating -LibraryServer $LibServer -VM $VM
PS C:\> $LibRating
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets the library server object named LibraryServer01 and stores the object in the $LibServer variable.

The third command gets the placement rating for LibraryServer01 (which indicates whether VMM can use a SAN transfer to transfer VM01 to LibraryServer01) and stores the rating object in the $LibRating variable.

The last command displays the rating stored in $LibRating.

Note: If a SAN transfer is not possible, you can use a LAN transfer to store the virtual machine in the library.

### Example 2: Get placement ratings for each available library server
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $LibServer = Get-SCLibraryServer 
PS C:\> $LibRating = Get-SCLibraryRating -LibraryServer $LibServer -VM $VM
PS C:\> $LibRating
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all library server objects that are managed by VMM and stores the objects in the $LibServer array.

The fourth command returns the placement rating for each library server object in $LibServer (which indicates whether VMM can use a SAN transfer to transfer VM01 to each of the library servers) and stores the rating for each library server object in the $LibRating array.

The last command displays the rating information for each library object.

Note: If a SAN transfer is not possible, you can use a LAN transfer to store the virtual machine in the library.

## PARAMETERS

### -LibraryServer
Specifies an array of VMM library server objects.

```yaml
Type: LibraryServer[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
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

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

