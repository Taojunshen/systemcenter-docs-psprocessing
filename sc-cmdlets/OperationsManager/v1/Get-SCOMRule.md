---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187706
schema: 2.0.0
ms.assetid: C24C3E68-2A55-4D78-87FA-7C6A3DE12D7E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRule.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRule.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCOMRule.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMRule

## SYNOPSIS
Gets Operations Manager monitoring rules.

## SYNTAX

### Empty (Default)
```
Get-SCOMRule [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromMonitoringRuleName
```
Get-SCOMRule -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromMonitoringDisplayRuleName
```
Get-SCOMRule [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromMonitoringRuleId
```
Get-SCOMRule -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPack
```
Get-SCOMRule [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCOMRule [-Target] <ManagementPackClass[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMRule** cmdlet gets monitoring rules for System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Get monitoring rules by specifying names with wildcard
```
PS C:\>Get-SCOMRule -Name "*health*"
```

This command gets all monitoring rules that have health in their name.

### Example 2: Get monitoring rules by specifying display names with a wildcard
```
PS C:\>Get-SCOMRule -DisplayName "*performance*"
```

This command gets all monitoring rules with performance in their display name.

### Example 3: Get a monitoring rule by specifying a management pack
```
PS C:\>Get-SCOMManagementPack -DisplayName "System Center Core Monitoring" | Get-SCOMRule
```

This command gets all management packs with System Center Core Monitoring in their display names.
It then uses the pipeline operator to send the management pack objects to the **Get-SCOMRule** cmdlet, which gets the monitoring rules for each management pack object.

### Example 4: Get monitoring rules by specifying target classes with a wildcard
```
PS C:\>Get-SCOMRule -Target (Get-SCOMClass -DisplayName "*health*")
```

This command gets the monitoring rules for each target class that has health in its display name.

### Example 5: Get monitoring rules by specifying a management pack with path:
```
PS C:\>$MPFile = "D:\Program Files\System Center Operations Manager 2007\Microsoft.SystemCenter.2007.mp"
PS C:\> Get-SCOMRule -ManagementPack $MPFile
```

This example gets monitoring rules for a management pack in a specified path.

The first command gets the path to a management pack file and stores it in the $MPFile variable.

The second command uses the *ManagementPack* parameter to get the monitoring rules from the management pack that is stored in the $MPFile variable.

### Example 6: Get a monitoring rule by specifying a GUID
```
PS C:\>Get-SCOMRule -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the monitoring rule that has an ID of 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be started on the computer.
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
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about credential objects, type `Get-Help Get-Credential`.

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

### -DisplayName
Specifies an array of display names for objects.
This cmdlet takes the strings in this array and looks for matches among the **DisplayName** properties of the objects that the cmdlet works with.
*DisplayName* values depend on the localized, imported management packs that are part of the management group and the locale of the user who runs Windows PowerShell

If this parameter does not appear, the default description is the one in the *Name* parameter.

```yaml
Type: String[]
Parameter Sets: FromMonitoringDisplayRuleName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies an array of IDs for monitoring rules.
The cmdlet gets monitoring rules that match the GUIDs.

An **SCOMGroup** object stores the GUID in its Id property.
To get the GUID of a class, type Get-SCOMGroup | Format-Table DisplayName, Id.

```yaml
Type: Guid[]
Parameter Sets: FromMonitoringRuleId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies a management pack object that stores overrides.
To obtain a management pack object, use the **Get-SCOMManagementPack** cmdlet.
If the rule is in an unsealed management pack, you must save the override into the same management pack.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of object names.

This parameter takes each string in the array and looks for matches among the Name properties of the objects that the cmdlet works with.

```yaml
Type: String[]
Parameter Sets: FromMonitoringRuleName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter is not specified, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

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

### -Target
Specifies an array of **ManagementPackClass** objects.
To obtain a **ManagementPackClass** object, use the **Get-SCClass** cmdlet.
The cmdlet gets monitoring rules for these classes.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
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

[Disable-SCOMRule](xref:OperationsManager/v1/Disable-SCOMRule.md)

[Enable-SCOMRule](xref:OperationsManager/v1/Enable-SCOMRule.md)

