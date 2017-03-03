---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 29369F56-C0CB-4ECB-92E4-EA635E9E9B44
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMonitor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMonitor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMonitor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMMonitor

## SYNOPSIS
Retrieves monitors in Operations Manager.

## SYNTAX

### Empty (Default)
```
Get-SCOMMonitor [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromMonitoringDisplayRuleName
```
Get-SCOMMonitor [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromMonitoringRuleId
```
Get-SCOMMonitor -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMO
```
Get-SCOMMonitor [-Instance] <EnterpriseManagementObject[]> [-Recurse] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCOMMonitor [-Recurse] [-Target] <ManagementPackClass[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCOMMonitor [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromMonitorName
```
Get-SCOMMonitor -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMMonitor** cmdlet retrieves monitors in System Center 2016 - Operations Manager.
In Operations Manager, monitors define logic for determining the health of an object.

## EXAMPLES

### Example 1: Retrieve a monitor by using a name
```
PS C:\>Get-SCOMMonitor -Name "System.Health*"
```

This command retrieves all monitors whose names begin with the string "System.Health".

### Example 2: Retrieve a monitor by using a display name
```
PS C:\>Get-SCOMMonitor -DisplayName "*Performance*"
```

This command retrieves all monitors whose display names contain the string "Performance".

### Example 3: Retrieve monitors for a management pack
```
PS C:\>Get-SCOMManagementPack -DisplayName "System Center Core Library" | Get-SCOMMonitor
```

This command retrieves the management pack that has the display name of System Center Core Library, and then passes the management pack object to the **Get-SCOMMonitor** cmdlet by using the pipeline operator (|).
The **Get-SCOMMonitor** cmdlet gets all monitors for the management pack object.

### Example 4: Retrieve monitors from a management pack
```
PS C:\>$MPFile = "C:\Program Files\System Center Operations Manager 2007\Microsoft.SystemCenter.2007.mp"
PS C:\> Get-SCOMMonitor -ManagementPack $MPFile
```

This example retrieves monitors in a management pack.

The first command gets the path to a management pack file and stores the value in the variable named $MPFile.

The second command uses the **Get-SCOMMonitor** cmdlet with the *ManagementPack* parameter to get the monitors from the management pack.

### Example 5: Retrieve monitors by display name
```
PS C:\>$Instances = Get-SCOMClass -DisplayName "*health*" | Get-SCOMClassInstance
PS C:\> Get-SCOMMonitor -Instance $Instances
```

This example retrieves monitors by display name.

The first command gets all classes that contain "health" in their display names, and then uses the pipeline operator (|) to pass the class objects to the **Get-SCOMClassInstance** cmdlet.
The **Get-SCOMClassInstance** cmdlet gets the instance for each class, and then stores the results in the $Instances variable.

The second command gets the monitors for the class instances stored in the $Instances variable.

### Example 6: Retrieve monitors by using a target class
```
PS C:\>Get-SCOMMonitor -Target (Get-SCOMClass -DisplayName *health*)
```

This example retrieves monitors by using a target class.

This command gets the monitors that have target classes that include "health" in their display names.

### Example 7: Retrieve a monitor by using an ID
```
PS C:\>Get-SCOMMonitor -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command retrieves the monitor that has the ID 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

## PARAMETERS

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
Specifies a **PSCredential** object for the computer or computers that the *ComputerName* parameter specifies.
The management group connection runs under this credential.
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

### -DisplayName
Specifies an array of display name objects.
Values of the *DisplayName* parameter may vary depending on which localized management packs a user imports into the management group and the locale of the user who is running Windows PowerShell.

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
Specifies an array of unique identifiers for monitors.

The **SCOMMonitor** object stores the GUID in the **Id** property of the object.
For more information, type "`Get-SCOMMonitor | Format-Table DisplayName, Id`".

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

### -Instance
Specifies an array of class instance objects.
The *Instance* parameter also accepts group objects as input.
For information about how to get a class instance object, type "`Get-Help Get-SCOMClassInstance`".

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromEMO
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies one or more management pack objects where you can save the override.
If an unsealed management pack contains the monitor, save the override in the same management pack.
For information about how to get a management pack object, type "`Get-Help Get-SCOMManagementPack`".

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
Specifies an array of names of an object.

```yaml
Type: String[]
Parameter Sets: FromMonitorName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -Recurse
Indicates that the cmdlet searches recursively.

```yaml
Type: SwitchParameter
Parameter Sets: FromEMO, FromManagementPackClass
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
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

### -Target
Specifies an array of monitors for one or more target class objects.
For information about how to get a class object, type "`Get-Help Get-SCOMClass`".

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

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

