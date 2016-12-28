---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2E438D0B-2616-4A8C-9B6E-E287D5510A38
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSSHKey.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSSHKey.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSSHKey.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSSHKey

## SYNOPSIS
Updates the properties of a Linux SSHKey.

## SYNTAX

### Default
```
Set-SCSSHKey [-UserRole <UserRole>] [-Enabled <Boolean>] [-VMMServer <ServerConnection>] [-SSHKey] <SSHKey>
 [-Name <String>] [-SharePath <String>] [-Description <String>] [-Owner <String>] [-FamilyName <String>]
 [-Release <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EquivalencySet
```
Set-SCSSHKey [-VMMServer <ServerConnection>]
 [-SSHKeys] <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SSHKey]>
 -FamilyName <String> -Release <String> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSSHKey** cmdlet updates the properties of a Linux **SSHKey** object stored in the Virtual Machine Manager (VMM) Library.

## EXAMPLES

### Example 1: Change the description of an SSHKey
```
PS C:\> $SSHKey = Get-SCSSHKey -VMMServer "VMMServer01.Contoso.com" | where { $_.LibraryServer.Name -eq "LibraryServer01.Contoso.com" -and $_.Name -eq "My.sshkey" }
PS C:\> Set-SCSSSHKey -SSHKey $sshkey -Description "My standard SSHKey"
```

The first command gets the **SSHKey** object named My.sshkey from the library on VMMServer01, and then stores that object in the $SSHKey variable.

The second command changes the description of the **SSHKey** stored in $SSHKey to "My standard SSHKey."

### Example 2: Change a property for an SSHKey
```
PS C:\> $SSHKey = Get-SCSSHKey -Name "My.sshkey"
PS C:\> Set-SCSSHKey -SSHKey $SSHKey -FamilyName "Family01"
```

The first command gets the **SSHKey** object named My.sshkey, and then stores that object in the $SSHKey variable.

The second command sets the **FamilyName** property to Family01 on the **SSHKey** object stored in $SSHKey.

## PARAMETERS

### -Description
Specifies a description for the **SSHKey** object.

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
Indicates whether to enable or disable the **SSHKey** object.
Specify $True to enable the **SSHKey** or $False to disable it.

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
Specifies a variable in which job progress is tracked and stored.

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
Specifies the name of a VMM **SSHKey** object.

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
Specifies the owner of the VMM **SSHKey** object in the form of a valid domain user account.

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

### -SSHKey
Specifies a Linux Administrator **SSHKey** object.

```yaml
Type: SSHKey
Parameter Sets: Default
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SSHKeys
Specifies a list of Linux Administrator **SSHKey** objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.SSHKey]
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

### LinuxAdministratorSshKey
This cmdlet returns a **LinuxAdministratorSshKey** object.

## NOTES

## RELATED LINKS

[Get-SCSSHKey](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSSHKey.md)

[Remove-SCSSHKey](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSSHKey.md)

