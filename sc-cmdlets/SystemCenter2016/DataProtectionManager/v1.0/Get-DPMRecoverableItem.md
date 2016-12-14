---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 148931AC-6D52-43F6-A49E-EAA5EA2E2991
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMRecoverableItem.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMRecoverableItem.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1.0/Get-DPMRecoverableItem.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMRecoverableItem

## SYNOPSIS
Gets a list of recoverable items in a recovery point.

## SYNTAX

### Browse (Default)
```
Get-DPMRecoverableItem [-RecoverableItem] <RecoverableObject> [-BrowseType] <BrowseType> [-Async]
 [-Tag <Object>] [<CommonParameters>]
```

### Shares
```
Get-DPMRecoverableItem -RecoveryPointForShares <RecoverySource> [-Async] [-Tag <Object>] [<CommonParameters>]
```

### Search
```
Get-DPMRecoverableItem [-Datasource] <Datasource> [-SearchOption] <SearchSpecifications> [-Async]
 [-Tag <Object>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMRecoverableItem** cmdlet gets a list of recoverable items in a recovery point for System Center 2016 - Data Protection Manager (DPM).
The recoverable items based on source are as follows: 

- File system: Files and folders
- Microsoft Exchange Server: Storage groups, databases, and mailboxes
- Microsoft SQL Server: Databases
- Microsoft SharePoint: Sites, databases, and documents
- Virtual Machines
- A DPM server
- System state of a protected computer

## EXAMPLES

### Example 1: Get a recoverable item in a recovery point
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $PObjects = Get-DPMDatasource -ProtectionGroup $PGroup
PS C:\> $RPoint = Get-DPMRecoveryPoint -Datasource $PObjects
PS C:\> Get-DPMRecoverableItem -RecoverableItem $RPoint -BrowseType Child
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores the group in the $PGroup variable.

The second command gets the list of protected and unprotected data in the protection group in $PGroup.
The command stores the result in the $PObjects variable.

The third command gets the recovery point for the protection group in $PObjects variable, and then stores the recovery point in the $RPoint variable.

The final command gets the recoverable items in the parent and child nodes of the recovery point in $RPoint.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

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

### -BrowseType
Specifies whether to browse only the parent nodes in a recovery point, or to browse the parent nodes and the child nodes.

The acceptable values for this parameter are:

- Parent
- Child

```yaml
Type: BrowseType
Parameter Sets: Browse
Aliases: 
Accepted values: Child, Parent

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Datasource
Specifies a data source object for which this cmdlet gets recoverable items.
A data source can be a file system share or volume for the Windows operating system, Microsoft SQL Server database, Microsoft Exchange Server storage group, Microsoft SharePoint farm, Microsoft Virtual Machine, DPM database, or system state that is a member of a protection group.

```yaml
Type: Datasource
Parameter Sets: Search
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoverableItem
Specifies a recoverable item object.
This is a child item in a recovery point that is recoverable.
Examples include the following: a file system share or volume, a Microsoft SQL Server database, a Microsoft Exchange Server storage group, Microsoft SharePoint Site, Microsoft Virtual Machine, a Microsoft DPM database, system state or a recovery point.

```yaml
Type: RecoverableObject
Parameter Sets: Browse
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPointForShares
Specifies a recovery point object.
To obtain a recovery point object, use the Get-DPMRecoveryPoint cmdlet.

```yaml
Type: RecoverySource
Parameter Sets: Shares
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SearchOption
Specifies the search options.
You can use the New-DPMSearchOption cmdlet to create an object that specifies search options for recoverable objects.

```yaml
Type: SearchSpecifications
Parameter Sets: Search
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Specifies a custom property that distinguishes the replies to each asynchronous call.
You can use parameter if you build a graphical user interface by using cmdlets.
Do not use this parameter if you work with the DPM Management Shell.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### RecoverableItem

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMProtectionGroup.md)

[Get-DPMRecoveryPoint](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMRecoveryPoint.md)

[New-DPMSearchOption](xref:SystemCenter2016/DataProtectionManager/v1.0/New-DPMSearchOption.md)

[Restore-DPMRecoverableItem](xref:SystemCenter2016/DataProtectionManager/v1.0/Restore-DPMRecoverableItem.md)

[Get-DPMDatasource](xref:SystemCenter2016/DataProtectionManager/v1.0/Get-DPMDatasource.md)

