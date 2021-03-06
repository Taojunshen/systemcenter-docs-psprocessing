---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AB00E9D3-C91F-4DAB-AB02-E752AF09485B
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Read-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Read-SCStorageProvider

## SYNOPSIS
Retrieves updated information from the storage provider including array, pool, and logical unit information exposed by the provider.

## SYNTAX

```
Read-SCStorageProvider [-Force] [-StorageProvider] <StorageProvider> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCStorageProvider** cmdlet retrieves updated information from the storage provider including array, pool, and logical unit information exposed by the provider.

## EXAMPLES

### Example 1: Refresh information about a storage provider
```
PS C:\> $Provider = Get-SCStorageProvider -Name "StorProv01.Contoso.com"
PS C:\> Read-SCStorageProvider -StorageProvider $Provider
```

The first command gets the storage provider named StorProv01 and stores it in the $Provider variable.

The second command retrieves updated information about the storage provider stored in the $Provider variable.

## PARAMETERS

### -Force
Forces the command to run without asking for user confirmation.

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

### -StorageProvider
Specifies a storage provider object.

```yaml
Type: StorageProvider
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageProvider
This cmdlet returns a **StorageProvider** object.

## NOTES

## RELATED LINKS

[Add-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCStorageProvider.md)

[Get-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageProvider.md)

[Import-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Import-SCStorageProvider.md)

[Remove-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageProvider.md)

[Set-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageProvider.md)

