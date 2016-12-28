---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F1256350-D1DD-49CA-8FC8-A4A31D9001EF
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceProtectionOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceProtectionOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMDatasourceProtectionOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMDatasourceProtectionOption

## SYNOPSIS
Sets protection options for a DPM data source.

## SYNTAX

### ExchangeOptions
```
Set-DPMDatasourceProtectionOption [-EseutilCheckType <EseutilTypeType>] [-BackUpType <AllowedBackupTypeType>]
 [[-TopologyType] <ProtectionTopologyType>] [[-PreferredPhysicalNode] <String[][]>]
 [-ProtectionGroup] <ProtectionGroup> [-Datasource <Datasource>] [-ExchangeOptions]
 [-RunEseUtilConsistencyCheck] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileExclusionRemoveOptions
```
Set-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-FileType] <String> [-Remove]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FileExclusionAddOptions
```
Set-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-FileType] <String> [-Add] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ClientFileSpecOptions
```
Set-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-Path] <String>
 [-ClientFileSpecOperation] <ClientFileSpecOperationType> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AllowClientUserToAddFileSpecs
```
Set-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup>
 [-AllowClientUserToAddFileSpecs] <Boolean> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AutoConsistencyCheck
```
Set-DPMDatasourceProtectionOption [-ProtectionGroup] <ProtectionGroup> [-AutoConsistencyCheck] <Boolean>
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMDatasourceProtectionOption** cmdlet sets protection options for a System Center 2016 - Data Protection Manager (DPM) data source.
You can set the following protection options:

- Exclude all files of a particular type from protection.
- Remove exclusions. 
- Set protection options for a Microsoft Exchange Server data source.

## EXAMPLES

### Example 1: Set a consistency check for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> Set-DPMDatasourceProtectionOption -ProtectionGroup $PGroup -AutoConsistencyCheck $True
```

The first command gets the protection groups from the server named DPMServer02, and then stores the result in the $PGroup variable.

The second command sets an automatic consistency check to run on all protection groups in $PGroup.

## PARAMETERS

### -Add
Indicates that the cmdlet adds a file exclusion to a protection group.

```yaml
Type: SwitchParameter
Parameter Sets: FileExclusionAddOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllowClientUserToAddFileSpecs
Indicates whether the user can specify which folders to protect.

```yaml
Type: Boolean
Parameter Sets: AllowClientUserToAddFileSpecs
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutoConsistencyCheck
Indicates whether DPM automatically runs consistency checks on the data sources of a protection group if a replica becomes inconsistent.

```yaml
Type: Boolean
Parameter Sets: AutoConsistencyCheck
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackUpType
Indicates the type of backup.

The acceptable values for this parameter are:

- CopyBackup
- FullBackup

```yaml
Type: AllowedBackupTypeType
Parameter Sets: ExchangeOptions
Aliases: 
Accepted values: FullBackup, CopyBackup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClientFileSpecOperation
Indicates which folders to add to the inclusion list or remove from the exclusion list.

The acceptable values for this parameter are:

- AddInclude
- RemoveInclude
- AddExclude
- RemoveExclude

```yaml
Type: ClientFileSpecOperationType
Parameter Sets: ClientFileSpecOptions
Aliases: 
Accepted values: AddInclude, RemoveInclude, AddExclude, RemoveExclude

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies a data source object.
A data source can be a file system share or volume, SQL Server database, Exchange Server storage group, Microsoft SharePoint farm, virtual machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: ExchangeOptions
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EseutilCheckType
Indicates how to run the Exchange Server database repair tool Eseutil.

The acceptable values for this parameter are:

- DontRun
- RunOnLogs
- RunOnLogsAndDB

```yaml
Type: EseutilTypeType
Parameter Sets: ExchangeOptions
Aliases: 
Accepted values: DontRun, RunOnLogs, RunOnLogsAndDB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExchangeOptions
Indicates that this cmdlet operates on Exchange Server data sources.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileType
Specifies a file type to include in or exclude from a protection group.

```yaml
Type: String
Parameter Sets: FileExclusionRemoveOptions, FileExclusionAddOptions
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -Path
Specifies the path of a folder to add to the inclusion list or remove from the exclusion list.

```yaml
Type: String
Parameter Sets: ClientFileSpecOptions
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredPhysicalNode
Specifies an array of names of servers to protect for Preferred Server topology.
This parameter applies only to servers that use cluster continuous replication in Microsoft Exchange Server 2007.

```yaml
Type: String[][]
Parameter Sets: ExchangeOptions
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group on which this cmdlet operates.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Remove
Indicates that this cmdlet performs a remove operation.

```yaml
Type: SwitchParameter
Parameter Sets: FileExclusionRemoveOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunEseUtilConsistencyCheck
Indicates that the cmdlet runs Eseutil consistency checking.
This parameter applies only to Exchange Server data sources.

```yaml
Type: SwitchParameter
Parameter Sets: ExchangeOptions
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TopologyType
Specifies the topology type.

The acceptable values for this parameter are:

- Active
- Passive
- Active if Passive Not Available

This parameter applies only to Microsoft Exchange Server 2007 installations that run cluster continuous replication.

```yaml
Type: ProtectionTopologyType
Parameter Sets: ExchangeOptions
Aliases: 
Accepted values: PT_CCR_PHYSICAL_NODE, PT_CCR_ACTIVE_ONLY, PT_CCR_PASSIVE_ONLY, PT_CCR_ACTIVE_IF_NO_PASSIVE

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Datasource

## NOTES

## RELATED LINKS

[Get-DPMDatasourceProtectionOption](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasourceProtectionOption.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

