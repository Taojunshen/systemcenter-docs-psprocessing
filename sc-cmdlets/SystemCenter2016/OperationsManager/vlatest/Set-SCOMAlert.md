---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E980654B-4665-4FB6-A04D-3B92EF7C8A9A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMAlert.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMAlert.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMAlert.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCOMAlert

## SYNOPSIS
Changes the properties of alerts.

## SYNTAX

```
Set-SCOMAlert -Alert <MonitoringAlert[]> [-Connector <MonitoringConnector>] [[-CustomField1] <String>]
 [[-CustomField2] <String>] [[-CustomField3] <String>] [[-CustomField4] <String>] [[-CustomField5] <String>]
 [[-CustomField6] <String>] [[-CustomField7] <String>] [[-CustomField8] <String>] [[-CustomField9] <String>]
 [[-CustomField10] <String>] [[-ResolutionState] <Byte>] [[-Owner] <String>] [[-TicketId] <String>]
 [-TfsWorkItemId <String>] [-TfsWorkItemOwner <String>] [[-Comment] <String>] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMAlert** cmdlet changes the properties of one or more alerts.
You can use the cmdlet to resolve an alert by setting the *ResolutionState* parameter to 255 (Closed).

## EXAMPLES

### Example 1: Close alerts by using the resolution state
```
PS C:\>Get-SCOMAlert -ResolutionState 15 | Set-SCOMAlert -ResolutionState 255
```

This command gets all alerts with a resolution state of 15 and then passes the alert objects to the **Set-SCOMAlert** cmdlet by using the pipe operator.
The **Set-SCOMAlert** cmdlet closes the alert by setting the resolution state to 255.

### Example 2: Change the properties of alerts
```
PS C:\>Get-SCOMAlert -Name "Failed Accessing Windows Event Log" | Set-SCOMAlert -Owner "CONTOSO\Isabel" -CustomField1 "Root Cause - Permissions"
```

This command gets all alerts named "Failed Accessing Windows Event Log" and then passes the alert objects to the **Set-SCOMAlert** cmdlet by using the pipe operator.
The **Set-SCOMAlert** cmdlet changes the owner of the alert and sets the value for CustomField1.

## PARAMETERS

### -Alert
Specifies an array of **MonitoringAlert** objects.
To obtain a **MonitoringAlert** object, use the **Get-SCOMAlert** cmdlet.

```yaml
Type: MonitoringAlert[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Connector
Specifies a **MonitoringConnector** object.
This parameter specifies the connector that generated the connection string.
To obtain a **MonitoringConnector** object, use the **Get-SCOMConnector** cmdlet.

```yaml
Type: MonitoringConnector
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField1
Specifies information to add to the **CustomField1** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField10
Specifies information to add to the **CustomField10** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField2
Specifies information to add to the **CustomField2** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField3
Specifies information to add to the **CustomField3** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField4
Specifies information to add to the **CustomField4** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField5
Specifies information to add to the **CustomField5** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField6
Specifies information to add to the **CustomField6** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField7
Specifies information to add to the **CustomField7** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField8
Specifies information to add to the **CustomField8** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomField9
Specifies information to add to the **CustomField9** property of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the user name of the owner of the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 13
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResolutionState
Specifies a resolution state Id.

When Operations Manager generates an alert, its resolution state is New.
You can change the resolution state for a new alert to Closed or to a custom resolution state that an administrator has created for the management group.
The ID for New is 0 and the ID for Closed is 255.
You can assign custom resolution states any value from 2 through 254.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TicketId
Specifies a value for the **TicketId** property for the alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 14
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Comment
Specifies a comment to add to the resolved alert.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
By default, this cmdlet does not generate any output.

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

### -TfsWorkItemId


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TfsWorkItemOwner


```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-SCOMAlert](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMAlert.md)

[Resolve-SCOMAlert](xref:SystemCenter2016/OperationsManager/vlatest/Resolve-SCOMAlert.md)

[Get-SCOMConnector](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMConnector.md)

