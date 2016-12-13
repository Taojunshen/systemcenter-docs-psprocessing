---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Import-SCLibraryPhysicalResource.md
schema: 2.0.0
ms.assetid: 8201AC2F-D629-49C1-A355-5041A28FE41C
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Export-SCLibraryPhysicalResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Export-SCLibraryPhysicalResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Export-SCLibraryPhysicalResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Export-SCLibraryPhysicalResource

## SYNOPSIS
Exports a library resource form a VMM library share to a local file folder or network share.

## SYNTAX

```
Export-SCLibraryPhysicalResource [-Path] <String> -Resource <ItemBase> [-OverwriteExistingFiles]
 [-AllowUnencryptedTransfer] [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-SCLibraryPhysicalResource** cmdlet exports (copies) a library resource from a Virtual Machine Manager (VMM) library share to a local file folder or network share.

## EXAMPLES

### Example 1: Export a specific library resource to a local file folder
```
PS C:\>$Resource = Get-SCVirtualHardDisk -Name "VHD01.vhd"
PS C:\> Export-SCLibraryPhysicalResource -Resource $Resource -Path "C:\ExportedLibResources" -OverwriteExistingFiles
```

The first command gets the virtual hard disk object named VHD01 and stores the object in the $Resource variable.

The second command exports the resource stored in $Resource to the folder named C:\ExportedLibResources.
If the resource had been previously exported to this folder, this command would overwrite any of those files.

### Example 2: Export a library resource to a network share
```
PS C:\>$Resource = Get-SCApplicationPackage -Name "WebApp01.zip"
PS C:\> Export-SCLibraryPhysicalResource -Resource $Resource -Path "\\FileShare01\LibExports"
```

The first command gets the application package object named WebApp01.zip and stores the object in the $Resource variable.

The second command exports the library resource stored in $Resource to the network share named \\\\FileShare01\LibExports.

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

### -Path
Specifies the destination path for the operation. 



Example formats: 


Local:       `-Path "F:\"`

UNC:         `-Path "\\\\Library\Templates"`

Volume GUID: `-Path "\\\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`

VMware ESX:  `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`
Citrix XenServer: -`Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

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

### -Resource
Specifies a resource object.

```yaml
Type: ItemBase
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Import-SCLibraryPhysicalResource](xref:VirtualMachineManager/v1/Import-SCLibraryPhysicalResource.md)

