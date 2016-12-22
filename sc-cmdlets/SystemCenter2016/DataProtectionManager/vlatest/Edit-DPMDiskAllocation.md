---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F6F0CD99-0D08-4F97-A0FC-02A8BCA307AA
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Edit-DPMDiskAllocation.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Edit-DPMDiskAllocation.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Edit-DPMDiskAllocation.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Edit-DPMDiskAllocation

## SYNOPSIS
Modifies disk allocation for a protected data source on a DPM server.

## SYNTAX

### ConnectedDatasource (Default)
```
Edit-DPMDiskAllocation [-Datasource] <Datasource> [-ReplicaSize <Int64>] [-ShadowCopySize <Int64>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DisconnectedClient
```
Edit-DPMDiskAllocation [-Datasource] <Datasource> [-ShadowCopySize <Int64>]
 [-ExpectedDataSizePerClientInMB <Int64>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Edit-DPMDiskAllocation** cmdlet modifies disk allocation on a System Center 2016 - Data Protection Manager (DPM) server for a protected data source.

## EXAMPLES

### Example 1: Modify the size of the replica and recovery point volumes
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> Edit-DPMDiskAllocation -Datasource $PObjects[1] -ReplicaSize 5368709120 -ShadowCopySize 3221225472
```

The first command uses the [Get-DPMProtectionGroup](./Get-DPMProtectionGroup.md) cmdlet to get the protection group for the server named Contoso-DPMServer.
The command stores the group in the $PGroup variable.

The second command uses the [Get-DPMDatasource](./Get-DPMDatasource.md) cmdlet to get all data source objects for the protection group stored in $PSGroup.
The command stores the objects in the $PObjects variable.

The last command modifies the size of the replica volume and the shadow copy volume for the second data source object stored in the $PObjects array.

## PARAMETERS

### -Datasource
Specifies a data source object for which this cmdlet modifies disk allocation.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ExpectedDataSizePerClientInMB
Specifies the new expected size, in megabytes, of data that DPM backs up from each client computer.

```yaml
Type: Int64
Parameter Sets: DisconnectedClient
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReplicaSize
Specifies the new size of a replica volume, in bytes.

```yaml
Type: Int64
Parameter Sets: ConnectedDatasource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShadowCopySize
Specifies the new size of a recovery point volume, in bytes.

```yaml
Type: Int64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

## NOTES

## RELATED LINKS

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMDatasource.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)
