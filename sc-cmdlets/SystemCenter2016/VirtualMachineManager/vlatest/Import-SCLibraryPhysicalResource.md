---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Export-SCLibraryPhysicalResource.md
schema: 2.0.0
ms.assetid: ABA52F8C-4F62-4EA6-A763-5764182EBC76
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Import-SCLibraryPhysicalResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Import-SCLibraryPhysicalResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Import-SCLibraryPhysicalResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SCLibraryPhysicalResource

## SYNOPSIS
Imports a resource into the VMM library.

## SYNTAX

```
Import-SCLibraryPhysicalResource [-SourcePath] <String> [[-SharePath] <String>] [-OverwriteExistingFiles]
 [-AllowUnencryptedTransfer] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCLibraryPhysicalResource** cmdlet imports a resource into the Virtual Machine Manager (VMM) library.
Self-service users can only import resources into their designated user role data path or a folder under that path.

## EXAMPLES

### Example 1: Import a library resource by an administrator or delegated administrator
```
PS C:\>Import-SCLibraryPhysicalResource -SourcePath "C:\AdminFolder\VHD01.vhd" -SharePath "\\VMMLibraryServer\MSSCVMMLibrary\ImportedLibraryResources" -OverwriteExistingFiles
```

This command imports the virtual hard disk named VHD01.vhd stored in the folder named C:\AdminFolder into the specified library path.
If a resource with that name already exists in that library path, this command will overwrite those files.

### Example 2: Import a library resource by a self-service user by specifing a path under the default user role data path in the VMM library
```
PS C:\>Import-SCLibraryPhysicalResource -SourcePath "C:\SSFolder\VHD01.vhd" -SharePath "\\<DefaultUserRoleDataPath>\SSUserSubfolder\Folder01"
```

This command imports the virtual hard disk named VHD01 from the folder named C:\SSFolder to the SSUserSubFolder\Folder01 folder stored under the default user role data path for the self-service user role of which the logged on user is a member.

### Example 3: Import a library resource by a self-service user to the default user role data path in the VMM library
```
PS C:\>Import-SCLibraryPhysicalResource -SourcePath "C:\SSFolder\VHD01.vhd"
```

This command imports the file named VHD01.vhd stored in C:\SSFolder to the default user role data path for the self-service user role of which the logged on user is a member.

## PARAMETERS

### -AllowUnencryptedTransfer
Indicates that network file transfers do not require encryption.
If you allow unencrypted network file transfers, it can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 

- Allow unencrypted file transfers into, or out of, the library. 
- Allow unencrypted file transfers into, out of, or within a host group.

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

### -OverwriteExistingFiles
Indicates that files with the same name are overwritten when importing or exporting resources into or out of the VMM library.

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

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path. 



Example format: `-SharePath "\\\\LibServer01\LibShare"`

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourcePath
Specifies the path to the resource that will be imported.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

## NOTES

## RELATED LINKS

[Export-SCLibraryPhysicalResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Export-SCLibraryPhysicalResource.md)

