---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: B7D3494C-7055-4F67-A44B-015752257800
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationPackage.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationPackage.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationPackage.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCApplicationPackage

## SYNOPSIS
Modifies the properties of an application package.

## SYNTAX

### Default (Default)
```
Set-SCApplicationPackage [-UserRole <UserRole>] [-Enabled <Boolean>] [-VMMServer <ServerConnection>]
 [-ApplicationPackage] <ApplicationPackage[]> [-EncryptionKey <PSCredential>] [-Name <String>]
 [-SharePath <String>] [-Description <String>] [-Owner <String>] [-FamilyName <String>] [-Release <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCApplicationPackage [-VMMServer <ServerConnection>] [-ApplicationPackage] <ApplicationPackage[]>
 [-SetAsEquivalent] -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCApplicationPackage** cmdlet modifies the properties of an application package stored in the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Update the description for an application package
```
PS C:\> $AppPackage = Get-SCApplicationPackage -Name "WebApp01.zip"
PS C:\> Set-SCApplicationPackage -ApplicationPackage $AppPackage -Description "Web application to install on a service."
```

The first command gets the application package object named WebApp01.zip and stores the object in the $AppPackage variable.

The second command updates the description for WebApp01.zip.

## PARAMETERS

### -ApplicationPackage
Specifies an array of application package objects.

```yaml
Type: ApplicationPackage[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
States a description for the specified object.

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

### -EncryptionKey
Specifies credentials to be used as an encryption key when you add a Hyper-V host located in a perimeter network to VMM.

Example format: `-SecurityFile "C:\SecurityFile.txt" -EncryptionKey $Key`

```yaml
Type: PSCredential
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

### -SetAsEquivalent
Indicates that the cmdlet marks multiple application packages as equivalent.

```yaml
Type: SwitchParameter
Parameter Sets: EquivalencySet
Aliases: 

Required: True
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

### ApplicationPackage
This cmdlet returns an **ApplicationPackage** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationPackage.md)

[Remove-SCApplicationPackage](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCApplicationPackage.md)

