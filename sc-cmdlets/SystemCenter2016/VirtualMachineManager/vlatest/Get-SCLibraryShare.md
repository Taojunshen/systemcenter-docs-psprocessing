---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5DE02B25-E2F6-4845-B265-FBB2477B70A1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCLibraryShare

## SYNOPSIS
Gets VMM library shares.

## SYNTAX

```
Get-SCLibraryShare [-VMMServer <ServerConnection>] [-ID <Guid>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCLibraryShare** cmdlet gets Virtual Machine Manager (VMM) library shares.

A library share is a Windows share on a VMM library server that is used to store files that contain library resources.
Resources can include virtual machine templates, hardware profiles, guest operating system profiles, virtual hard disks (Windows-based .vhd files, Citrix XenServer-based .vhd files or VMware-based .vmdk files), virtual floppy disks (Windows-based .vfd files or VMware-based .flp files), ISO images (.iso files), and scripts, as well as stored virtual machines.

For more information about library shares, type `Get-Help Add-LibraryShare -Detailed`.

## EXAMPLES

### Example 1: Get all library shares
```
PS C:\> Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com"
```

This command gets all library share objects from the VMM library on VMMServer01 and displays information about these library shares to the user.

### Example 2: Get a specific library share on the specified library server
```
PS C:\> $LibShare = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AllVHDs" }
```

This command gets the library share object named AllVHDs (on library server LibraryServer01) from the library on VMMServer01 and then stores the share object in the $LibShare variable.

### Example 3: Get all library shares on a specific library server
```
PS C:\> $LibServer = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "LibraryServer01.Contoso.com"
PS C:\> $AllLibShares = Get-SCLibraryShare | where { $_.LibraryServer.Name -eq "$LibServer" } 
PS C:\> $AllLibShares | Get-Member
```

The first command retrieves the library server object named LibraryServer01 from the library on VMMServer01 and stores it in the $LibServer variable.

The second command gets all library share objects on LibraryServer01 and stores the objects in the $AllLibShares variable.

The last command passes each object in $AllLibShares to the **Get-Member** cmdlet, which displays the .NET type for a library share object and the list of methods and properties that are associated with a VMM library share object.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

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

### LibraryShare
This cmdlet returns a **LibraryShare** object.

## NOTES

## RELATED LINKS

[Add-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryShare.md)

[Find-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Find-SCLibraryShare.md)

[Read-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLibraryShare.md)

[Remove-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLibraryShare.md)

[Set-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLibraryShare.md)

