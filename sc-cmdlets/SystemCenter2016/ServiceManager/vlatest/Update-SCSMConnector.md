---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7EA649EF-9AD3-4403-A547-FD4FD2169613
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Update-SCSMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Update-SCSMConnector

## SYNOPSIS
Updates the properties of a Service Manager connector.

## SYNTAX

```
Update-SCSMConnector [-Connector] <Connector[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMConnector** cmdlet updates the properties of a Service Manager connector.
For example, you can set the **Enable** property to $False to disable the connector, or you can set it to $True to enable the connector.
Use this cmdlet conjunction with the Get-SCSMConnector cmdlet.
After **Get-SCSmConnector** retrieves the object, you can modify the properties of the object, and then pass it to the current cmdlet.
This cmdlet updates the properties.

The **schedule** property is only available if you have applied Service Manager 2012 R2 Update Rollup 6 or later.

For each connector type, you can update the following properties:

Active Directory Connector

- Description
- Enable
- Name
- RunAsAccount
- SelectedObjects
- Schedule

Configuration Manager Connector

- Collections
- Description
- Enable
- Name
- RunAsAccount
- Schedule

Operations Manager Alert Connector

- CloseAlert
- Description
- Enable
- Name
- ResolveIncident
- Rules
- RunAsAccount
- Schedule
- Template

Operations Manager CI Connector

- Description
- Enable
- Name
- OperationsManagerServer
- RunAsAccount
- Schedule

## EXAMPLES

### Example 1: Update objects in an Active Directory connector
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -RunAsProfileName "NewProfile"
PS C:\> $ADConnector = Get-SCSMConnector -Name "WOODGROVE Active Directory"
PS C:\> $ADConnector.Select = "(&(objectCategory=computer)(name=*fulle*))"
PS C:\> Get-SCSMConnector | ForEach-Object { $_.RunAsAccount = $RunAsAccount } | Update-SCSMConnector
```

This example updates the selected objects of an Active Directory connector.
The first command gets a Run As account, by using the Get-SCSMRunAsAccount cmdlet, and then stores it in the $RunAsAccount variable.

The second command gets a connector by using the **Get-SCSMConnector** cmdlet, and then stores it in the $ADConnector variable.

The third command assigns a value to the **Select** property of $ADConnector.

The final command gets all connectors, and then passes those that use the $RunAsAccount as the Run As account to the current cmdlet.
That cmdlet updates the connectors.

### Example 2: Update the Run As account for connectors
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -RunAsProfileName "NewProfile"
PS C:\> Get-SCSMConnector | ForEach-Object { $_.RunAsAccount = $RunAsAccount } | Update-SCSMConnector
```

The first command gets the Run As account that has the profile name NewProfile, and then stores the result in the $RunAsAccount variable.

The second command updates all connectors that have the Run As account of $RunAsAccount.

### Example 3: Update an Operations Manager Alert connector
```
PS C:\>$AlertConnector = Get-SCSMConnector "Alert Connector"
PS C:\>$AlertConnector.rules += New-SCSMAlertRule @{
>> Name = "newRule"
>> Template = Get-SCSMObjectTemplate -Name ".*IncidentTemplate.*"
>> ManagementPack = Get-SCManagementPack "System.Library"
>>}
PS C:\>Update-SCSMConnector -Connector $AlertConnector
```

This example adds a new rule to an Operations Manager Alert connector.
The first command gets a connector, and then stores it in the $AlertConnector variable.

The second command adds a rule to the **rules** property of $AlertConnector.
The New-SCSMAlertRule cmdlet creates the rule.
The command extends over several lines.

The final command updates the connector to the current value of $AlertConnector.

## PARAMETERS

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

### -Connector
Specifies an object that represents a Service Manager connector.

```yaml
Type: Connector[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the connector that it updates.
You can pass this object to other cmdlets.

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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Connectors.Connector
You can pipe a connector to the *Connector* parameter.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMConnector.md)

[New-SCSMAlertRule](xref:SystemCenter2016/ServiceManager/vlatest/New-SCSMAlertRule.md)

[Remove-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMConnector.md)

[Start-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Start-SCSMConnector.md)

