---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Find-SCLibraryShare.md
schema: 2.0.0
ms.assetid: 6D37715E-5B3E-44AA-97A3-E0BA94661DC6
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCLibraryShare

## SYNOPSIS
Adds Windows shares on the file system of a library server to the VMM library as library shares.

## SYNTAX

```
Add-SCLibraryShare [-VMMServer <ServerConnection>] [-SharePath] <String> [-Credential <PSCredential>]
 [-Description <String>] [-AddDefaultResources] [-JobGroup <Guid>] [-UseAlternateDataStream <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCLibraryShare** cmdlet adds Windows shares on the file system of a library server to the Virtual Machine Manager (VMM) library as library shares.

Before you can add a library share to the VMM library, you must first create the share in the Windows file system.
You can, for example, use Windows Explorer to create and share a folder that you want to add to the library.

If you create a Windows share at the same level as the default library share (MSSCVMMLibrary) created by VMM Setup or on a separate library server, use the **Add-SCLibraryShare** cmdlet to add that share to the VMM library.

If you create a Windows folder under the default VMM library share (MSSCVMMLibrary), VMM automatically scans the share, discovers all existing objects stored on that share that qualify as library objects, and adds the library objects to the library.
However, you can use the **Read-SCLibraryShare** cmdlet to manually refresh that share and import its contents into the VMM library.

Note: Library resources that can be discovered only by the library refresher but not created by an administrator include virtual hard disks (Windows-based .vhd files, Citrix XenServer-based .vhd files or VMware-based .vmdk files), virtual floppy disks (Windows-based .vfd files or VMware-based .flp files), ISO images (.iso files), and scripts.

## EXAMPLES

### Example 1: Add a Windows share as a library share object to the VMM library
```
PS C:\>Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> Add-SCLibraryShare -SharePath "\\LibraryServer01\AllVHDs"
```

The first command connects to VMMServer01.

The second command adds a library share object to the library named AllVHDs (a Windows share located on LibraryServer01).
This example assumes that LibraryServer01 is already a VMM library server.

### Example 2: Add two Windows shares as library share objects to the VMM library
```
PS C:\>Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> $SharePaths = "\\LibraryServer01\AllVHDs", "\\LibraryServer01\AllISOs"
PS C:\> ForEach($SharePath in $SharePaths) { Add-SCLibraryShare -SharePath $SharePath }
```

The first command connects to VMMServer1.

The second command stores the strings "\\\\LibraryServer01\AllVHDs" and "\\\\LibraryServer01\AllSOs" in the $SharePaths variable.
This example assumes that LibraryServer01 is already a VMM library server.

The last command uses a **ForEach** loop to pass the two share names stored in $SharePaths to the **Add-SCLibraryShare** cmdlet, which adds each Windows share as a library share to VMM.

Note: For more information about the standard Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.
The **ForEach** loop statement is not the same as the ForEach-Object cmdlet, which uses **ForEach** as an alias.

## PARAMETERS

### -AddDefaultResources
Indicates that the default resources for a library share are added.

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

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task. 



For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the library share.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path. 



Example format: `-SharePath "\\\\LibServer01\LibShare"`

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

### -UseAlternateDataStream
Specifies whether or not to use the Use AlternateDataStream.

```yaml
Type: Boolean
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

[Find-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Find-SCLibraryShare.md)

[Get-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryShare.md)

[Read-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCLibraryShare.md)

[Remove-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLibraryShare.md)

[Set-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLibraryShare.md)

