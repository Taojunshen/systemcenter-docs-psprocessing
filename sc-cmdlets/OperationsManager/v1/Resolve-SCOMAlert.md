---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239493
schema: 2.0.0
ms.assetid: CD68FFFE-7792-4E14-91B8-CDC631E59F6E
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Resolve-SCOMAlert.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Resolve-SCOMAlert.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Resolve-SCOMAlert.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Resolve-SCOMAlert

## SYNOPSIS
Resolves an alert.

## SYNTAX

```
Resolve-SCOMAlert -Alert <MonitoringAlert[]> [-Connector <MonitoringConnector>] [[-CustomField1] <String>]
 [[-CustomField2] <String>] [[-CustomField3] <String>] [[-CustomField4] <String>] [[-CustomField5] <String>]
 [[-CustomField6] <String>] [[-CustomField7] <String>] [[-CustomField8] <String>] [[-CustomField9] <String>]
 [[-CustomField10] <String>] [[-Owner] <String>] [[-TicketId] <String>] [-TfsWorkItemId <String>]
 [-TfsWorkItemOwner <String>] [[-Comment] <String>] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Resolve-SCOMAlert** cmdlet resolves an alert in System Center 2016 - Operations Manager.
The cmdlet sets the **ResolutionState** property of an alert to 255 (Closed).
You can also resolve an alert by using the **Set-SCOMAlert** cmdlet and setting the *ResolutionState* parameter to 255 (Closed).

## EXAMPLES

### Example 1: Resolve error alerts by using the alert severity
```
PS C:\>Get-SCOMAlert -Severity 2 | Resolve-SCOMAlert -Comment "All alerts are resolved."
```

This command resolves all Error alerts and adds a comment to the resolved alerts.

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
Specifies the user name of the owner of the alert, in the format Domain\Account.

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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TicketId
Specifies the ticket ID of the alert.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMAlert](xref:OperationsManager/v1/Get-SCOMAlert.md)

[Set-SCOMAlert](xref:OperationsManager/v1/Set-SCOMAlert.md)

