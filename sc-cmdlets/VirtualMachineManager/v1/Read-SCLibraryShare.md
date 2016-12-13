---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryShare.md
schema: 2.0.0
ms.assetid: CB903ED4-6307-4B9E-B0BD-23F7AC55B301
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCLibraryShare

## SYNOPSIS
Updates the state and metadata of VMM library objects stored in a library share.

## SYNTAX

```
Read-SCLibraryShare [-LibraryShare] <LibraryShare> [-Path <String>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCLibraryShare** cmdlet updates the state and metadata of all Virtual Machine Manager (VMM) library objects stored in the specified library share.
This update also finds new library files on the specified library share as well as new child shared folders under the specified library share.

## EXAMPLES

### Example 1: Update a specified library share
```
PS C:\>$LibShare = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AllVHDs" }
PS C:\> Read-SCLibraryShare -LibraryShare $LibShare
```

The first command gets the library share object named AllVHDs on LibraryServer01 from the VMM library on VMMServer01 and then stores the object in the $LibShare variable.

The second command updates the state and metadata information for all library objects in the share stored in $LibShare, and then it adds any new library objects found in the share to the VMM library.

### Example 2: Update multiple library shares
```
PS C:\>$LibShares = Get-SCLibraryShare -VMMServer "VMMServer1.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -match "vhd" }
PS C:\> $LibShares | Read-SCLibraryShare
```

The first command gets the library share objects on LibraryServer01 with the string "vhd" in their names, and then stores the objects in the $LibShares variable.

The second command updates the information for all library shares stored in $LibShares, and then it adds any new library objects found in these shares to the VMM library.

### Example 3: Update a specific subdirectory on a library share
```
PS C:\>$LibShare = Get-SCLibraryShare -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AllVHDs" }
PS C:\> Read-SCLibraryShare -LibraryShare $LibShare -Path "Production\WebFrontEnd"
```

The first command gets the library share object named AllVHDs on LibraryServer01 from the VMM library on VMMServer01 and then stores the object in the $LibShare variable.

The second command updates the state and metadata information for all library objects in the specified subdirectory on the library share that is stored in $LibShare, and then it adds any new library objects found in the share to the VMM library.

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

### -LibraryShare
Specifies a VMM library share object.

```yaml
Type: LibraryShare
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Path
Specifies the destination path for the operation. 



Example formats: 


Local path:       `-Path "F:\"`

UNC path:         `-Path "\\\\Library\Templates"`

Volume GUID path: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

VMware ESX path:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`

Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LibraryShare
This cmdlet returns a **LibraryShare** object.

## NOTES

## RELATED LINKS

[Add-SCLibraryShare](xref:VirtualMachineManager/v1/Add-SCLibraryShare.md)

[Find-SCLibraryShare](xref:VirtualMachineManager/v1/Find-SCLibraryShare.md)

[Get-SCLibraryShare](xref:VirtualMachineManager/v1/Get-SCLibraryShare.md)

[Remove-SCLibraryShare](xref:VirtualMachineManager/v1/Remove-SCLibraryShare.md)

[Set-SCLibraryShare](xref:VirtualMachineManager/v1/Set-SCLibraryShare.md)

