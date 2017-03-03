---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 54E520CC-5C1F-4482-80D9-F62B7CCD2A19
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceMode.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceMode.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMMaintenanceMode.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOMMaintenanceMode

## SYNOPSIS
Gets maintenance mode entries.

## SYNTAX

```
Get-SCOMMaintenanceMode [[-Instance] <MonitoringObject[]>] [-History] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMMaintenanceMode** cmdlet gets maintenance mode entries.
You can use this cmdlet to provide objects to the **Set-SCOMMaintenanceMode** cmdlet, or by itself to see details about maintenance mode entries.

When a resource is in maintenance mode, System Center 2016 - Operations Manager suppresses alerts, notifications, rules, monitors, automatic responses, state changes, and new alerts.

When you use this cmdlet by itself, it presents information for the local time.
If you pipe its results to the **Format-Table** cmdlet, the cmdlet provides information in Coordinated Universal Time (UTC).
For more information about **Format-Table**, type, `Get-Help Format-Table`.

By default, this cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

## EXAMPLES

### Example 1: Get all active maintenance mode entries
```
PS C:\>Get-SCOMMaintenanceMode
```

This command gets all active maintenance mode entries.
In order to include inactive entries, specify the *History* parameter.

### Example 2: Get all active maintenance mode entries for a specified domain
```
PS C:\>Get-SCOMMaintenanceMode -Instance (Get-SCOMClassInstance -Name "*.Contoso.com") -ErrorAction SilentlyContinue
```

This command gets all active maintenance mode entries for class instances in the Contoso.com domain.
The command uses the **Get-SCOMClassInstance** cmdlet to get the instances that contain Contoso.com.

If the command encounters a class instance that lacks active maintenance mode entries, the *ErrorAction* parameter allows the command to continue without displaying an error.

### Example 3: Get all maintenance mode entries for a specified domain
```
PS C:\>Get-SCOMClassInstance -Name "*.Contoso.com" | Get-SCOMMaintenanceMode -History
```

This command gets all class instances in the Contoso.com domain and then uses the pipeline operator (|) to pass the class instance objects to the **Get-SCOMMaintenanceMode** cmdlet.
This example uses the *History* parameter; therefore, the command gets all maintenance mode entries, including inactive entries.

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

### -History
Indicates that the cmdlet gets all maintenance mode entries, including inactive entries.
Without this parameter, the cmdlet gets only active maintenance mode entries.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Instance
Specifies an array of monitoring objects that represent instances.
To obtain monitoring objects, use the **Get-SCOMClassInstance** cmdlet.

This parameter also accepts group objects.
To obtain a group object, use the **Get-SCOMGroup** cmdlet.

```yaml
Type: MonitoringObject[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMClassInstance](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMClassInstance.md)

[Set-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMMaintenanceMode.md)

[Start-SCOMMaintenanceMode](xref:SystemCenter2016/OperationsManager/vlatest/Start-SCOMMaintenanceMode.md)

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMGroup.md)

