---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 83F1556A-7FD0-4231-AD62-96A2D029F5C7
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScript.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScript.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCScript.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCScript

## SYNOPSIS
Changes the properties of a script stored in the VMM library.

## SYNTAX

### Default
```
Set-SCScript [-UserRole <UserRole>] [-Enabled <Boolean>] [-VMMServer <ServerConnection>] [-Script] <Script>
 [-Name <String>] [-SharePath <String>] [-Description <String>] [-Owner <String>] [-FamilyName <String>]
 [-Release <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCScript [-VMMServer <ServerConnection>]
 [-Scripts] <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Script]>
 -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCScript** cmdlet changes one or more properties of a script stored in the Virtual Machine Manager (VMM) library.

Properties that you can change include: 

- Description
- Enabled
- Name
- Owner
- SharePath

Script objects represent script files stored in a library share on a library server.
Typically, these scripts are either Windows PowerShell® scripts or answer files (such as a Sysprep.inf or an Unattend.xml file) that contain the inputs required for the Windows Setup program.

## EXAMPLES

### Example 1: Change the description of a script
```
PS C:\> $Script = Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "Sysprep.inf" }
PS C:\> Set-SCScript -Script $Script -Description "Windows Server 2008 R2 Sysprep Answer File"
```

The first command retrieves the answer file script object named Sysprep.inf from the library on VMMServer01and then stores the object in the $Script variable.

The second command changes the description of this script object to "Windows Server 2008 R2 Sysprep Answer File".

### Example 2: Disable a Windows PowerShell script stored in the VMM library
```
PS C:\> $Script = Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "AddHost.ps1" }
PS C:\> Set-SCScript -Script $Script -Enabled $FALSE
```

The first command gets the the PowerShell script object named AddHost.ps1 and stores the object in the $Script variable.

The second command disables the script stored in $Script.

### Example 3: Specify an owner for all scripts with an unknown owner
```
PS C:\> Get-SCScript -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq "Unknown"} | Set-SCScript -Owner "Contoso\PattiFuller"
```

This command gets all script objects from the VMM library whose owner is Unknown, and then specifies an owner for each script object.

## PARAMETERS

### -Description
Specifies a description for the script.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Enables an object when set to $True, or disables an object when set to $False.
For example, if you want to upgrade software on a virtual machine template, you can disable the template object in the VMM library to temporarily prevent users from using that object.

```yaml
Type: Boolean
Parameter Sets: Default
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
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: EquivalencySet
Aliases: 

Required: True
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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

```yaml
Type: String
Parameter Sets: Default
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

### -Release
Specifies a string that describes the release of a library resource.
VMM automatically creates a release value for every resource imported into the library.
After the resource has been imported, the string can be customized.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: EquivalencySet
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

### -Script
Specifies a VMM script object.

```yaml
Type: Script
Parameter Sets: Default
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Scripts
Specifies an array of script objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.Script]
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path.

Example format: `-SharePath \\LibServer01\LibShare`.

```yaml
Type: String
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.

```yaml
Type: UserRole
Parameter Sets: Default
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
* Requires a VMM script object, which can be retrieved by using the **Get-SCScript** cmdlet.

## RELATED LINKS

[Get-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCScript.md)

[Remove-SCScript](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCScript.md)

