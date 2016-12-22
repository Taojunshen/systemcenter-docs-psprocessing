---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: dd490ed7-43ea-41e4-b24c-5fc7ae529858
schema: 2.0.0
ms.assetid: 1473CEF5-6891-4457-B7EF-7B082892A3A9
updated_at: 12/20/2016 5:21 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSupportedRecoveryPointObjective.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSupportedRecoveryPointObjective.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/485d58d80386539445685faae8425bdc96723376/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSupportedRecoveryPointObjective.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSupportedRecoveryPointObjective

## SYNOPSIS
Gets a supported recovery point objective for a virtual machine.

## SYNTAX

```
Get-SCSupportedRecoveryPointObjective [-VMMServer <ServerConnection>] -VMID <Guid> [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSupportedRecoveryPointObjective** cmdlet gets the supported recovery point objective for a virtual machine.

## EXAMPLES


## PARAMETERS

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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -VMID
Specifies the unique ID of a virtual machine.

```yaml
Type: Guid
Parameter Sets: (All)
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

