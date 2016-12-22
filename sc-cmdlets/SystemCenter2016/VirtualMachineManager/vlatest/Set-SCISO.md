---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 10990465-FD8D-486A-BFEF-C8043924FE76
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCISO.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCISO.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCISO.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCISO

## SYNOPSIS
Changes the properties of an ISO object.

## SYNTAX

### Default
```
Set-SCISO [-UserRole <UserRole>] [-Enabled <Boolean>] [-VMMServer <ServerConnection>] [-ISO] <ISO>
 [-Name <String>] [-SharePath <String>] [-Description <String>] [-Owner <String>] [-FamilyName <String>]
 [-Release <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCISO [-VMMServer <ServerConnection>]
 [-ISOs] <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ISO]>
 -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCISO** cmdlet changes one or more properties of an ISO object used in a Virtual Machine Manager (VMM) environment.
Properties that you can change include: 



- Description

- Enabled

- Name

- Owner

- SharePath

## EXAMPLES

### Example 1: Change the owner of an ISO file
```
PS C:\> $ISO = @(Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "OsISO.iso" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" } )
PS C:\> Set-SCISO -ISO $ISO[0] -Owner "Contoso\PattiFuller"
```

The first command gets all ISO objects named "OsISO.iso" from LibraryServer01 and stores the ISO objects in an array named $ISO.

The second command changes the owner of the first ISO object stored in the $ISO array to Patti Fuller, a member of the Contoso.com domain.

### Example 2: Specify an owner for all ISO objects with an unknown owner
```
PS C:\> Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where {$_.Owner -eq "Unknown"} | Set-ISO -Owner "Contoso\PattiFuller"
```

This command gets all ISO objects from the VMM library whose owner is Unknown, and then specifies an owner for each ISO object.

### Example 3: Disable an ISO object stored in the VMM library
```
PS C:\> $ISO = Get-SCISO -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -eq "OsISO.iso" -and $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" }
PS C:\> Set-SCISO -ISO $Iso -EnableLibraryObject $FALSE
```

The first command gets the ISO object named OsISO.iso from LibraryServer01 and stores the object in the $ISO variable.

The second command disables the ISO object stored in the $ISO variable.

## PARAMETERS

### -Description
Specifies a description for the ISO object.

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

### -ISO
Specifies an ISO object.

```yaml
Type: ISO
Parameter Sets: Default
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ISOs
Specifies an array of ISO objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.ISO]
Parameter Sets: EquivalencySet
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -SharePath
Specifies a path to a valid library share on an existing library server that uses a Universal Naming Convention (UNC) path. 

Example format: `-SharePath "\\LibServer01\LibShare"`

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

### ISO
This cmdlet returns an **ISO** object.

## NOTES
* Requires a VMM **ISO** object, which can be retrieved by using the **Get-SCISO** cmdlet.

## RELATED LINKS

[Get-SCISO](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCISO.md)

[Remove-SCISO](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCISO.md)

