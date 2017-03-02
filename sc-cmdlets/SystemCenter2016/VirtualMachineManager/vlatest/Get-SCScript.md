---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 54F8CB65-5E69-4018-8173-38C727177BA1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCScript

## SYNOPSIS
Gets script objects from the VMM library, which allows you to view or edit any script, or to view, edit, or run a Windows PowerShell script if you have appropriate permissions.

## SYNTAX

### All (Default)
```
Get-SCScript [-VMMServer <ServerConnection>] [-All] [<CommonParameters>]
```

### NameParamSet
```
Get-SCScript [-VMMServer <ServerConnection>] -Name <String> [<CommonParameters>]
```

### EquivalentResourceParamSet
```
Get-SCScript [-VMMServer <ServerConnection>] [-Release <String>] -FamilyName <String> [<CommonParameters>]
```

### ID
```
Get-SCScript [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCScript** cmdlet gets script objects from the Virtual Machine Manager (VMM) library.
The script file that a script object represents is stored in the file system on a library server.
Typically, these scripts are either Windows PowerShell® scripts or answer file scripts (including Sysprep.inf and Unattend.xml files, which contain the inputs required for the Windows Setup program).

As illustrated in the examples, you can use **Get-SCScript** not only to retrieve script objects but also, if you have appropriate permissions, to view the contents of a script or to edit a script.
In addition, you can run the script if the following are true: 1) the script is a Windows PowerShell script, 2) scripting is enabled on your server, and 3) you have appropriate permissions (see example 5).

For information about enabling Windows PowerShell scripting on your server, type `Get-Help about_Signing`, `Get-Help Get-ExecutionPolicy -Detailed`, and `Get-Help Set-ExecutionPolicy -Detailed`.

## EXAMPLES

### Example 1: Get all scripts stored on all VMM library servers
```
PS C:\> Get-SCScript -VMMServer "VMMServer01.Contoso.com"
```

This command gets all script objects stored in library shares in the VMM library on VMMServer01, and then displays information about these scripts to the user.

### Example 2: Display specified information about all scripts on a library server
```
PS C:\> Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" } | Format-List -Property Name, LibraryServer, SharePath
```

This command gets all script objects stored on LibraryServer01 and displays the name, library server, and share path for these scripts to the user.

### Example 3: Get all scripts with a specific name on any VMM library server
```
PS C:\> Get-SCScript -VMMServer "VMMServer1.Contoso.com" | where { $_.Name -eq "Sysprep.inf" }
```

This command gets the answer file script objects named Sysprep.inf that are stored on any library server on VMMServer01.

Note: By default, the name of a script object in the VMM library is the same name, including the file extension, as the name of the actual script file on the library server.

### Example 4: View a script that is stored in the VMM library
```
PS C:\> $Script = Get-SCScript | where { $_.Name -eq "SummarizeVMMInfo.ps1"}
PS C:\> Notepad.exe $Script.SharePath
```

The first command gets the script object named SummarizeVMMInfo.ps1 from the VMM library and stores the object in the $Script variable.

The second command uses Notepad to open the script so that you can view its contents if you have the appropriate permissions to read the script.

Note: If you have appropriate write permissions, you can also edit the script and save the new version.

### Example 5: Run a Windows PowerShell script that is stored in the VMM library
```
PS C:\> $Script = Get-SCScript | where { $_.Name -eq "SummarizeVMMInfo.ps1" }
PS C:\> &$Script.SharePath
```

The first command gets the script object named "SummarizeVMMInfo.ps1" from the VMM library and stores the object in the $Script variable.

The second command uses the ampersand (&) operator to run the script stored in $Script.

To run a Windows PowerShell script stored in a VMM library share, you must ensure the following: 

- You have read and execute permissions on the script file. 
- You are member of the VMM Administrators user role. 
- You have permissions to access the VMM library share. 
- Windows PowerShell scripting is enabled.
If it isn't: 

     1.
Run the VMM command shell as an Administrator. 
      2.
Use the **Set-ExecutionPolicy** cmdlet to set the execution policy to the appropriate level for your environment. 

For more information, type `Get-Help about_Signing`, `Get-Help Get-ExecutionPolicy -Detailed`, and `Get-Help Set-ExecutionPolicy -Detailed`

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

### -FamilyName
Specifies a family name for a physical resource in the VMM library.
This value is used in conjunction with Release, Namespace, and Type to establish equivalency among library resources.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
Aliases: 

Required: True
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
Parameter Sets: NameParamSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Release
Specifies a string that describes the release of a library resource.
VMM automatically creates a release value for every resource imported into the library.
After the resource has been imported, the string can be customized.

```yaml
Type: String
Parameter Sets: EquivalentResourceParamSet
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

### Script
This cmdlet returns a **Script** object.

## NOTES

## RELATED LINKS

[Remove-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScript.md)

[Set-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScript.md)

