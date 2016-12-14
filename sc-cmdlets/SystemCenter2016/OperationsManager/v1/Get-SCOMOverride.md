---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187713
schema: 2.0.0
ms.assetid: 81EE1031-66B1-494B-B290-1D373AFE5198
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMOverride.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMOverride.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMOverride.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMOverride

## SYNOPSIS
Retrieves a list of overrides or a resulting set of overrides.

## SYNTAX

### Empty (Default)
```
Get-SCOMOverride [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPackDiagnostic
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Diagnostic] <ManagementPackDiagnostic[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackDiscovery
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Discovery] <ManagementPackDiscovery[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackMonitor
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Monitor] <ManagementPackMonitor[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackRecovery
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Recovery] <ManagementPackRecovery[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackRule
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Rule] <ManagementPackRule[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromTask
```
Get-SCOMOverride [-Class <ManagementPackClass[]>] [-Instance <EnterpriseManagementObject[]>]
 [-Group <EnterpriseManagementObject[]>] [[-Task] <ManagementPackTask[]>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMOverride** cmdlet retrieves a list of overrides, or a resulting set of overrides.
In System Center 2016 - Operations Manager, overrides represent changes to parameters in monitors.

## EXAMPLES

### Example 1: Retrieve all overrides for a set of rules
```
PS C:\>Get-SCOMRule -Name "*health*" | Get-SCOMOverride -ErrorAction SilentlyContinue
```

This example gets all monitoring rules that contain the word health in their name, and then returns the overrides for the rule objects.

Using the *ErrorAction* parameter with the SilentlyContinue value allows the command to continue if it cannot find an override for a specific monitoring rule, and will not display an error.

### Example 2: Retrieve all overrides for a specific class
```
PS C:\>Get-SCOMOverride -Monitor (Get-SCOMMonitor -Name "*health*") -Class (Get-SCOMClass -DisplayName "*computer*")
```

This command gets the override for monitors that contain the word health in their name and are in a class with a display name that contains the word computer.

### Example 3: Retrieve all overrides for a set of discovery objects
```
PS C:\>Get-SCOMDiscovery -Name "*system*" | Get-SCOMOverride -ErrorAction SilentlyContinue
```

This command gets all discoveries that contain system in their name, and then returns the overrides for those discovery objects.

Using the *ErrorAction* parameter with the SilentlyContinue value allows the command to continue if it cannot find an override for a specific discovery, and will not display an error.

## PARAMETERS

### -Class
Specifies an array of class objects.
For more information, type `Get-Help Get-SCOMClass`.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackDiagnostic, FromManagementPackDiscovery, FromManagementPackMonitor, FromManagementPackRecovery, FromManagementPackRule, FromTask
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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
For more information, type "`Get-Help Get-Credential`".

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

### -Diagnostic
Specifies an array of diagnostic objects.
For more information about how to get a diagnostic object, type "`Get-Help Get-SCOMDiagnostic`".

```yaml
Type: ManagementPackDiagnostic[]
Parameter Sets: FromManagementPackDiagnostic
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Discovery
Specifies an array of discovery objects.
For more information about how to get a discovery object, type "`Get-Help Get-SCOMDiscovery`".

```yaml
Type: ManagementPackDiscovery[]
Parameter Sets: FromManagementPackDiscovery
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Group
Specifies an array of group objects.
For more information about how to get a group object, type "`Get-Help Get-SCOMGroup`".

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromManagementPackDiagnostic, FromManagementPackDiscovery, FromManagementPackMonitor, FromManagementPackRecovery, FromManagementPackRule, FromTask
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an array of class instance objects.
This parameter also accepts group objects.
For more information about how to get a class instance object, type "`Get-Help Get-SCOMClassInstance`".

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromManagementPackDiagnostic, FromManagementPackDiscovery, FromManagementPackMonitor, FromManagementPackRecovery, FromManagementPackRule, FromTask
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Monitor
Specifies an array of monitor objects.
For more information about how to get a monitor object, type "`Get-Help Get-SCOMMonitor`".

```yaml
Type: ManagementPackMonitor[]
Parameter Sets: FromManagementPackMonitor
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Recovery
Specifies an array of recovery objects.
For more information about how to get a recovery object, type "`Get-Help Get-SCOMRecovery`".

```yaml
Type: ManagementPackRecovery[]
Parameter Sets: FromManagementPackRecovery
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Rule
Specifies an array of monitoring rule objects.
For more information about how to get a monitoring rule object, type "`Get-Help Get-SCOMRule`".

```yaml
Type: ManagementPackRule[]
Parameter Sets: FromManagementPackRule
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

### -Task
Specifies an array of task objects.
For more information about how to get a task object, type "`Get-Help Get-SCOMTask`".

```yaml
Type: ManagementPackTask[]
Parameter Sets: FromTask
Aliases: 

Required: False
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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMClassInstance.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMGroup.md)

[Get-SCOMDiagnostic](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMDiagnostic.md)

[Get-SCOMMonitor](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMMonitor.md)

[Get-SCOMRecovery](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMRecovery.md)

[Get-SCOMRule](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMRule.md)

[Get-SCOMTask](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMTask.md)

