---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 502011D2-FE9C-47B3-84B6-1F7ACC4A8ADE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDatasourceConsistencyCheck.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDatasourceConsistencyCheck.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Start-DPMDatasourceConsistencyCheck.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Start-DPMDatasourceConsistencyCheck

## SYNOPSIS
Performs a consistency check on a DPM data source.

## SYNTAX

### Datasource
```
Start-DPMDatasourceConsistencyCheck [-Datasource] <Datasource> [-HeavyWeight]
 [-JobStateChangedEventHandler <JobStateChangedEventHandler>] [-ForcedFullCC]
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ProtectionGroup
```
Start-DPMDatasourceConsistencyCheck [-ProtectionGroup] <ProtectionGroup>
 [[-AdhocJobsContext] <AdhocJobsContext>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Start-DPMDatasourceConsistencyCheck** cmdlet performs a consistency check on a System Center 2016 - Data Protection Manager (DPM) data source.
You can run consistency checks on a specific data source or on all data sources in a protection group that are in an inconsistent state.

## EXAMPLES

### Example 1: Start a consistency check on a data source
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName TestingServer
PS C:\> $PObject = Get-DPMDatasource $PGroup[0]
PS C:\> Start-DPMDatasourceConsistencyCheck -Datasource $PObject
```

The first command gets the protection groups from the server named TestingServer by using the **Get-DPMProtectionGroup** cmdlet.
The command stores them in the $PGroup variable.

The second command gets the data source for the first protection group in $PGroup, and then stores the data source in the $Ds variable.

The third command runs a consistency check on the data source that is stored in $Ds.

## PARAMETERS

### -AdhocJobsContext
Specifies the context details of the ad hoc job.
Do not use this parameter from the Windows PowerShell command line.

```yaml
Type: AdhocJobsContext
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies a data source object for which this cmdlet starts a consistency check.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: Datasource
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ForcedFullCC
Indicates that this cmdlet performs a heavyweight consistency check on all databases in the farm, not just on the databases in an inconsistent state.
This option is specific to SharePoint.

```yaml
Type: SwitchParameter
Parameter Sets: Datasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeavyWeight
Indicates that the cmdlet performs a heavyweight consistency check.
A heavyweight consistency check creates a checksum for the contents of each file.
This parameter affects only file servers.
The cmdlet always performs heavyweight consistency checks on application servers.

```yaml
Type: SwitchParameter
Parameter Sets: Datasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobStateChangedEventHandler
Specifies an event handler for **Job.StateChanged** events.
Use this parameter to build a graphical user interface based on cmdlets.
Do not use this parameter in the DPM Management Shell.

```yaml
Type: JobStateChangedEventHandler
Parameter Sets: Datasource
Aliases: Handler

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group which contains data sources on which this cmdlet runs a check.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: ProtectionGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

## NOTES

## RELATED LINKS

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

