---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCStorageZoneAlias.md
schema: 2.0.0
ms.assetid: E1703AFD-E950-472D-9198-532378E69783
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageZoneAlias.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageZoneAlias.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCStorageZoneAlias.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageZoneAlias

## SYNOPSIS
Creates a Fibre Channel zone alias.

## SYNTAX

```
New-SCStorageZoneAlias [-StorageFabric] <StorageFabric> -Name <String> [-Description <String>]
 [-AddZoneMembership <String[]>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageZoneAlias** cmdlet creates a Fibre Channel zone alias.

## EXAMPLES

### Example 1: Create a Fibre Channel zone alias
```
PS C:\>$Fabric = Get-SCStorageFabric -Name "PROD"
PS C:\> $Members = @()
PS C:\> $Members += "C003FF3B8A610000"
PS C:\> $Members += "D113EF3A8F411234"
PS C:\> New-SCStorageZoneAlias -StorageFabric $Fabric -Name "ZoneAlias01" -Description "" -AddZoneMembership $Members
```

The first command gets the storage fabric object named PROD, and then stores that object in the $Fabric variable.

The second command creates an array named $Members.
The third and fourth commands populate the $Members array.

The last command creates a zone alias named ZoneAlias01 for the members stored in $Members.

## PARAMETERS

### -AddZoneMembership
Specifies an array of zone members for this cmdlet to add.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the new zone alias.

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

### -JobVariable
Specifies the name of a variable that you use to track and store job progress.

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
Specifies the name of the new Fibre Channel zone alias.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### StorageZoneAlias
This cmdlet returns a **StorageZoneAlias** object.

## NOTES

## RELATED LINKS

[Get-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCStorageZoneAlias.md)

[Remove-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCStorageZoneAlias.md)

[Set-SCStorageZoneAlias](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCStorageZoneAlias.md)

