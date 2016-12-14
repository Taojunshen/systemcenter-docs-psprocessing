---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 5f0cc68f-147f-440b-b7ec-e6206f7e90ab
schema: 2.0.0
ms.assetid: 68F3EE1E-6E5A-4BE4-90C0-6586B42E17D0
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Publish-SCWindowsPE.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Publish-SCWindowsPE.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Publish-SCWindowsPE.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Publish-SCWindowsPE

## SYNOPSIS
Publishes an updated Windows PE image for use by all PXE servers in your VMM environment.

## SYNTAX

### UseCustomizedWinPE
```
Publish-SCWindowsPE [-VMMServer <ServerConnection>] [-RunAsynchronously] -Path <String> [-ISOPath <String>]
 [-IsUEFI] [<CommonParameters>]
```

### UseDefaultImage
```
Publish-SCWindowsPE [-VMMServer <ServerConnection>] [-RunAsynchronously] [-UseDefaultImage] [-ISOPath <String>]
 [-IsUEFI] [<CommonParameters>]
```

## DESCRIPTION
The **Publish-SCWindowsPE** cmdlet publishes an updated Windows Preinstallation Environment (Winows PE) image for use by all Pre-Boot EXecution Environment (PXE) servers in your Virtual Machine Manager (VMM) environment.

Note: This cmdlet must be run on the VMM management server.

Scenarios that require an updated Windows PE image: 

- The Windows Automated Installation Kit (AIK) is patched, or Microsoft issues a new version of Windows AIK. 
- The VMM agent binaries are patched. 
- You add your own drivers, or other custom files, to Windows PE.

Note: Customize the Windows PE image by adding drivers or custom files using standard Windows tools and then use this cmdlet to publish the updated Windows PE boot WIM image on a library share.

Each scenario requires that you use this cmdlet not only to add the updated Windows PE image to VMM but also to rebuild it.

Tasks that you perform by using this cmdlet include the following:

1.
Specify the source Windows PE image:

Option 1: Start from the standard Windows PE image from the Windows AIK that is currently installed on the VMM management server.
In this case, both x86 and x64 versions of Winows PE must be processed.

Option 2: Start from an existing Windows PE image on a VMM library share. 
   In this case, only the specified Windows PE image (which is either x86 or x64) 
   is processed.

Note: The Windows PE image chosen must not already contain the VMM agent.
If such a Windows PE image is chosen, an error is returned and the Windows PE image is not imported.

2.
Specify the Library Resource Folder in which to store the updated Windows PE image.

Note: VMM creates a folder named Boot WIMS with Agent on the target Library Resource Folder if it does not already exist.

3.
Construct a new Windows PE image from the source Winows PE image as follows:

a.
Copy the source Windows PE image into a temporary location on the VMM management server.

b.
Mount the WinPE image.

c.
Copy the agent files from the fixed location on the VMM management server into a fixed location in the Windows PE image.
Overwrite any files that already exist in the Windows PE image, but do not otherwise delete any files or directories.

d.
Perform Windows PE configuration tasks, such as setting the RAM disk size, ensuring that optional features like WMI are installed, and so on.

e.
Unmount the image and commit changes.

f.
Copy the updated Winows PE image into the Boot WIMs with Agent folder.

4.
Force discovery on the Library Resource Folder, and confirm that the newly placed Windows PE image appears in your VMM environment.

5.
Use **Publish-SCWindowsPE** to copy all Windows PE images in the Boot WIMs with Agent folder to all PXE servers, and to extract Windows network boot programs (NBP) on each PXE server.

## EXAMPLES

### Example 1: Update the Windows PE image with a custom Windows PE image base
```
PS C:\>Publish-SCWindowsPE -Path "\\LibraryServer02\VMMWinPE\ContosoIT.wim"
```

This command uses a customized base image to create a Windows PE image and updates all VMM PXE servers.

### Example 2: Re-create the Windows PE image and update the VMM PXE servers
```
PS C:\>Publish-SCWindowsPE -UseDefaultImage
```

This command re-creates the Windows PE image by using the Windows PE image from (or updated by) the Windows ADK.
It then updates all VMM PXE servers.

## PARAMETERS

### -ISOPath
Specifies the destination path for an ISO file.

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

### -IsUEFI
Indicates that the computer on which the operating system will be installed is Unified Extensible Firmware Interface (UEFI)-based.

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
Parameter Sets: UseCustomizedWinPE
Aliases: 

Required: True
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

### -UseDefaultImage
Indicates that new or updated Windows Preinstallation Environment (Windows PE) images are published by using the standard Windows PE images from the latest Windows Automated Deployment Kit (Windows ADK).

```yaml
Type: SwitchParameter
Parameter Sets: UseDefaultImage
Aliases: 

Required: True
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

## NOTES

## RELATED LINKS

