---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 53B00DA7-D1F3-4BB7-B0D6-93D5E22D36E6
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDatasource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDatasource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMDatasource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMDatasource

## SYNOPSIS
Gets protected and unprotected data in a computer or protection group.

## SYNTAX

### DpmServer (Default)
```
Get-DPMDatasource [[-DPMServerName] <String>] [-Inactive] [<CommonParameters>]
```

### DataSourceSearch
```
Get-DPMDatasource [[-DPMServerName] <String>] [-Query] <String> [<CommonParameters>]
```

### Search
```
Get-DPMDatasource [[-DPMServerName] <String>] [-Path] <String> [[-ProductionServerName] <String>]
 [<CommonParameters>]
```

### ClientProtectionGroup
```
Get-DPMDatasource [[-DPMServerName] <String>] [-Async] [-ComputerName] <String[]> [<CommonParameters>]
```

### ProductionServer
```
Get-DPMDatasource [-ProductionServer] <ProductionServer> [-Async] [-Inquire] [-Replica] [-Tag <Object>]
 [-IgnoreDPMInformation] [-GetVolumesWithoutMountPoints] [<CommonParameters>]
```

### ProtectionGroup
```
Get-DPMDatasource [-ProtectionGroup] <ProtectionGroup> [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMDatasource** cmdlet gets the protected and unprotected data on a computer in System Center 2016 - Data Protection Manager (DPM).
The output displays only objects at levels that allow you to apply protection.
Use the Get-DPMChildDatasource cmdlet to see files in the data source.

This cmdlet can also return the following information about the data on the computer.

The acceptable values for this parameter are:

- All available data sources on the protected computer.
- Protected data source on a DPM server.
- Inactive data sources on a DPM server.
An inactive data source is one that is not actively protected on a DPM server.
- Data sources in a protection group.

## EXAMPLES

### Example 1: Return all data sources on a computer
```
PS C:\>$DpmPServer = Get-DPMProductionServer -DPMServerName "TestingServer"
PS C:\> Get-DPMDatasource -ProductionServer $DpmPServer[1] -Inquire
```

The first command returns the servers that have DPM Protection Agent installed, and then stores them in the $DpmPServer variable.

The second command gets the data sources on the second server in $DpmPServer.

### Example 2: Return protected data sources in a protection group
```
PS C:\>$DpmPServer = Get-DPMProtectionGroup -DPMServerName "TestingServer"
PS C:\> Get-DPMDatasource -ProtectionGroup $DpmPServer
```

The first command returns the protection group from the DPM server named TestingServer.
The command stores the group in the $DpmPServer variable.

The second command returns the data sources from the protection group in $DpmPServer.

### Example 3: Return inactive data sources on a server
```
PS C:\>Get-DPMDatasource -DPMServerName "TestingServer" -Inactive
```

This command retrieves the inactive data sources on the DPM server named TestingServer.

### Example 4: Get a data source from a search location
```
PS C:\>Get-DPMDatasource -DPMServerName "TestingServer" -SearchPath "F:\" -ProductionServer "Test.contoso.com"
```

This command retrieves a data source from the search path F:\ on the protected server Test.contoso.com.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

```yaml
Type: SwitchParameter
Parameter Sets: ClientProtectionGroup, ProductionServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of client computers that you add to the protection group.

```yaml
Type: String[]
Parameter Sets: ClientProtectionGroup
Aliases: ComputerNames

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of the DPM server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: DpmServer, DataSourceSearch, Search, ClientProtectionGroup
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GetVolumesWithoutMountPoints
Indicates that the cmdlet retrieves volumes without mount points.

```yaml
Type: SwitchParameter
Parameter Sets: ProductionServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreDPMInformation
Indicates that the cmdlet does not retrieve protected computer information for data sources.

```yaml
Type: SwitchParameter
Parameter Sets: ProductionServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inactive
Indicates that the cmdlet returns inactive data sources on a DPM server.
An inactive data source is one that was protected on the DPM server at one time but is not protected currently.
The replicas and recovery points of an inactive data source remain available.

```yaml
Type: SwitchParameter
Parameter Sets: DpmServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inquire
Indicates that this cmdlet queries the protected computer and returns the data sources or child data sources on it.

```yaml
Type: SwitchParameter
Parameter Sets: ProductionServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Specifies the path on which to search for the data source.

```yaml
Type: String
Parameter Sets: Search
Aliases: SearchPath

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductionServer
Specifies a computer on which a DPM protection agent is installed.

```yaml
Type: ProductionServer
Parameter Sets: ProductionServer
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ProductionServerName
Specifies the name of a computer on which a DPM protection agent is installed.

```yaml
Type: String
Parameter Sets: Search
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies the a protection group on which this cmdlet acts.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: ProtectionGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Query
Specifies a filter for of the data sources.
This cmdlet returns only the ones that have names that contain the specified string.

```yaml
Type: String
Parameter Sets: DataSourceSearch
Aliases: SearchQuery

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replica
Indicates that this cmdlet calculates the space that is required for a replica on the secondary DPM server from the protected computer or the primary DPM server.

```yaml
Type: SwitchParameter
Parameter Sets: ProductionServer
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Specifies a custom property that distinguishes the replies to each asynchronous call.
You can use parameter if you build a graphical user interface by using cmdlets.
Do not use this parameter if you work with the DPM Management Shell.

```yaml
Type: Object
Parameter Sets: ProductionServer
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

### Datasource

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMProductionServer](xref:DataProtectionManager/v1/Get-DPMProductionServer.md)

[Data Protection Manager Cmdlets](xref:DataProtectionManager/v1/DataProtectionManager.md)

