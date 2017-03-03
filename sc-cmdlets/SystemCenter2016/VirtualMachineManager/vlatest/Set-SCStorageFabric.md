---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 56A16D4D-304C-4AF1-8F06-E2CA092AFC36
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabric.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabric.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageFabric.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageFabric

## SYNOPSIS
Updates a storage Fibre Channel fabric object.

## SYNTAX

### Default (Default)
```
Set-SCStorageFabric [-StorageFabric] <StorageFabric> [-Name <String>] [-Description <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EnableManagement
```
Set-SCStorageFabric [-StorageFabric] <StorageFabric> [-Name <String>] [-Description <String>]
 [-EnableManagement] -StorageFabricClassification <StorageFabricClassification> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### DisableManagement
```
Set-SCStorageFabric [-StorageFabric] <StorageFabric> [-Name <String>] [-Description <String>]
 [-DisableManagement] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageFabric** cmdlet updates a storage Fibre Channel fabric object.

## EXAMPLES

### Example 1: Disable management of a storage fabric
```
PS C:\> $Fabric = Get-SCStorageFabric -Name "Fabric01"
PS C:\> Set-SCStorageFabric -StorageFabric $Fabric -DisableManagement
```

The first command gets the storage fabric object named Fabric01, and then stores that object in the $Fabric variable.

The second command disables management of the storage fabric object stored in $Fabric.

### Example 2: Enable management of a storage fabric
```
PS C:\> $Fabric = Get-SCStorageFabric -Name "Fabric01"
PS C:\> $Classification = Get-SCStorageFabricClassification -Name "PROD"
PS C:\> Set-SCStorageFabric -StorageFabric $Fabric -StorageFabricClassification $Classification -EnableManagement
```

The first command gets the sdtorage fabric object named Fabric01, and stores that object in the $Fabric variable.

The second command gets the storage fabric classification object named PROD by using the **Get-SCStorageFabricClassification** cmdlet.
The command stores that object in the $Classification variable.

The last command enables management of the storage fabric stored in $Fabric, and applies the storage classification stored in $Classification.

### Example 3: Modify name and description of a storage fabric
```
PS C:\> $fabric = Get-SCStorageFabric -Name "Fabric01"
PS C:\> Set-SCStorageFabric -StorageFabric $fabric -Name "newName" -Description "newDescription"
```

The first command gets the storage fabric object named Fabric01, and then stores that object in the $Fabric variable.

The second command applies a new name and a description to the storage fabric object stored in $Fabric.

### Example 4: Modify a storage fabric classification
```
PS C:\> $Fabric = Get-SCStorageFabric -Name "Fabric01"
PS C:\> $Classification = Get-SCStorageFabricClassification -Name "PROD"
PS C:\> Set-SCStorageFabric -StorageFabric $Fabric -StorageFabricClassification $Classification
```

The first command gets the storage fabric object named Fabric01, and then stores the object in the $Fabric variable.

The second command gets the storage fabric classification object named PROD, and then stores that object in the $Classification variable.

The last command applies the classification stored in $Classification to the storage fabric stored in $Fabric.

## PARAMETERS

### -Description
Specifies a description for the storage Fibre Channel fabric object.

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

### -DisableManagement
Indicates that this cmdlet disables management of the Fibre Channel fabric.

```yaml
Type: SwitchParameter
Parameter Sets: DisableManagement
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableManagement
Indicates that this cmdlet enables management of the Fibre Channel fabric.

```yaml
Type: SwitchParameter
Parameter Sets: EnableManagement
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
Specifies the name of the storage Fibre Channel fabric object that this cmdlet modifies.

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

### -StorageFabric
Specifies a storage Fibre Channel fabric object.

```yaml
Type: StorageFabric
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageFabricClassification
Specifies a classification for storage Fibre Channel fabric.

```yaml
Type: StorageFabricClassification
Parameter Sets: EnableManagement
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageFabric
This cmdlet returns a **StorageFabric** object.

## NOTES

## RELATED LINKS

[Get-SCStorageFabric](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabric.md)

[Get-SCStorageFabricClassification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageFabricClassification.md)

