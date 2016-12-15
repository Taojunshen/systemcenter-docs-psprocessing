---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: a5703917-d9f5-4e61-a19f-46b7ac7a7e8a
schema: 2.0.0
ms.assetid: 2661BB9D-A135-4AAA-B1E3-140A403336AC
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageTier.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageTier.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCStorageTier.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCStorageTier

## SYNOPSIS
Creates a Storage Tier configured with Virtual Machine Manager Server.

## SYNTAX

### NewTierSharedSpaces (Default)
```
New-SCStorageTier [-VMMServer <ServerConnection>] -MediaType <StoragePhysicalDiskMediaType> -SizeMB <UInt64>
 [-ResiliencySettingName <String>] [-PhysicalDiskRedundancy <UInt16>] [-NumberOfColumns <UInt16>]
 -JobGroup <Guid> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### NewTierS2D
```
New-SCStorageTier [-VMMServer <ServerConnection>] -StorageTierFriendlyName <String>
 -StorageTierSizeInMB <UInt64> -JobGroup <Guid> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCStorageTier** cmdlet creates a Storage Tier configured by using Virtual Machine Manager Server.
As part of creating the Storage Tier, you can specify the media type (HDD, SSD) underlying the storage tier and the resiliency (Simple, Mirroring, or Parity) to define the availability characteristics of the tier.

## EXAMPLES

### Example 1: Create a storage tier on non-S2D system
```
PS C:\>New-SCStorageTier -MediaType "SSD" -SizeMB 1024 -NumberOfColumns 2 -PhysicalDiskRedundancy
```

This command creates a storage tier on a non-S2D system.

### Example 2: Create a storage tier on S2D system
```
PS C:\>New-SCStorageTier -StorageTierFriendlyName "Performance" -StorageTierSizeInMB 1024 -RunAsynchronously -JobGroup "191de146-dbec-4955-a347-70edd4315c41"
```

This command creates a storage tier on an S2D system.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that run as a set just before the final command that includes the same job group identifier runs.

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

### -MediaType
Specifies an array of storage physical disk media type objects.
The acceptable values for this parameter are:

- HDD
- SSD

```yaml
Type: StoragePhysicalDiskMediaType
Parameter Sets: NewTierSharedSpaces
Aliases: 
Accepted values: Unknown, HDD, SSD

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NumberOfColumns
Specifies the number of columns for a virtual disk.

```yaml
Type: UInt16
Parameter Sets: NewTierSharedSpaces
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

### -PhysicalDiskRedundancy
Specifies the number of physical disk failures that a virtual disk can sustain.

```yaml
Type: UInt16
Parameter Sets: NewTierSharedSpaces
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResiliencySettingName
Specifies the resiliency setting for a virtual disk.
The acceptable values for this parameter are:

- Mirror
- Parity

```yaml
Type: String
Parameter Sets: NewTierSharedSpaces
Aliases: 
Accepted values: Simple, Mirror, Parity

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

### -SizeMB
Specifies the size, in megabytes, of a storage volume or file share.

```yaml
Type: UInt64
Parameter Sets: NewTierSharedSpaces
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierFriendlyName
Specifies an existing global storage tier name.
Supported on S2D system.

```yaml
Type: String
Parameter Sets: NewTierS2D
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageTierSizeInMB
{{Fill StorageTierSizeInMB Description}}

```yaml
Type: UInt64
Parameter Sets: NewTierS2D
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

