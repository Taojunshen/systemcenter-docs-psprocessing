---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-CloudVMRoleSizeProfile.md
schema: 2.0.0
ms.assetid: 31E4F5EC-B7F9-40A9-9C8A-4A2BE05FD289
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-CloudVMRoleSizeProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-CloudVMRoleSizeProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-CloudVMRoleSizeProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-CloudVMRoleSizeProfile

## SYNOPSIS
Gets a cloud virtual machine role size profile.

## SYNTAX

```
Get-CloudVMRoleSizeProfile [-Name <String>] [-VMMServer <ServerConnection>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-CloudVMRoleSizeProfile** cmdlet gets a cloud virtual machine role size profile.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

## NOTES

## RELATED LINKS

[New-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-CloudVMRoleSizeProfile.md)

[Remove-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-CloudVMRoleSizeProfile.md)

[Set-CloudVMRoleSizeProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-CloudVMRoleSizeProfile.md)
