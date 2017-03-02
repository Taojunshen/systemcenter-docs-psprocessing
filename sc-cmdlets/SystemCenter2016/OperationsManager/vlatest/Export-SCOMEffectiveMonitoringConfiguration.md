---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 1AFC3DCC-9D73-4BEB-8589-6DFADD696A54
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Export-SCOMEffectiveMonitoringConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Export-SCOMEffectiveMonitoringConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Export-SCOMEffectiveMonitoringConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Export-SCOMEffectiveMonitoringConfiguration

## SYNOPSIS
Exports configuration applicable to a monitoring object.

## SYNTAX

```
Export-SCOMEffectiveMonitoringConfiguration [-Instance] <MonitoringObject> [-Path] <String>
 [-Encoding <Encoding>] [-RecurseContainedObjects] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Export-SCOMEffectiveMonitoringConfiguration** cmdlet retrieves the rules, monitors, and overrides that apply to a specified monitoring object, calculates the effective configuration of the rules and monitors, and then saves the results to a .csv file.
This file uses the pipe symbol (|) as a separator.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Export monitoring configuration for a group of computers
```
PS C:\>$Members = (Get-SCOMGroup -DisplayName "All Windows Computers").GetRelatedMonitoringObjects()
PS C:\> $Members | ForEach-Object { Export-SCOMEffectiveMonitoringConfiguration -Instance $_ -Path "C:\temp\$($_.DisplayName).csv" } -RecurseContainedObjects }
```

This example exports the monitoring configuration for all the computers in a specified group of computers.

The first command gets the group members of the All Windows Computers group and stores the objects in the $Members variable.

The second command uses the pipeline operator to pass each object stored in the $Members variable to the **ForEach-Object** cmdlet, which includes the **Export-SCOMEffectiveMonitoringConfiguration** command that exports the data to a .csv file in the specified location.
The command includes the name of the computer in the file name, and appends a .csv extension.
For more information about **ForEach-Object**, type `Get-Help ForEach-Object`.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be running on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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

### -Credential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent instances.
To obtain a class instance object, use the **Get-SCOMClassInstance** cmdlet.

This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: MonitoringObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Path
Specifies the path and file name for the exported .csv file.
The cmdlet does not add a file name extension.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecurseContainedObjects
Indicates that the cmdlet exports all discovered data for the monitoring object that the *Instance* parameter specifies.
For example, in the case of a computer, the cmdlet exports all discoveries and monitors on the computer and all monitoring objects hosted or contained on the computer, such as disks or network cards.

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

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

```yaml
Type: Connection[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Encoding
Specifies the encoding to use for the monitoring configuration.

```yaml
Type: Encoding
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

## NOTES

## RELATED LINKS

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

