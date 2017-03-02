---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F0F5DECD-4B11-4FDE-A970-DBCCDD128D2D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCSMDCMWorkflow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSMDCMWorkflow

## SYNOPSIS
Creates a DCM workflow in Service Manager.

## SYNTAX

```
New-SCSMDCMWorkflow [-DisplayName] <String> [-ConfigurationBaseLine <Hashtable[]>] [-Description <String>]
 [-Enable <Boolean>] [-ManagementPack <ManagementPack>] [-Template <ManagementPackObjectTemplate>]
 [-EnableNotification <Boolean>] [-Notification <Hashtable[]>] [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMDCMWorkflow** cmdlet creates a Desired Configuration Management (DCM) workflow in Service Manager.

## EXAMPLES

### Example 1: Create a DCM workflow
```
PS C:\>$ManagementPack = Get-SCSMManagementPack -Name "*IncidentManagement.Configuration" 
PS C:\> $Template01 = Get-SCObjectTemplate -Name "AssignedToUserNotificationTemplate" 
PS C:\> $Template02 = Get-SCObjectTemplate -Name "HighPriorityIncidentTemplate" 
PS C:\> $Template03 = Get-SCObjectTemplate -Name "DefaultIncidentTemplate" 
PS C:\> New-SCSMDCMWorkflow -DisplayName "DCMWorkflow03" -Description "A DCM workflow" -Enable $False -EnableNotification $True -ManagementPack $ManagementPack -Notification @{User = "Assigned To User";Template = $Template01},@{User="Created By User";Template= $Template02} -Template $Template03 
PS C:\> Get-SCSMDCMWorkflow
DisplayName     Description           Enabled
-----------     -----------           -------
DCMWorkflow03   A DCM workflow        False
```

The first command gets a management pack that matches the string IncidentManagement.Configuration by using the Get-SCSMManagementPack cmdlet.
The command stores that object in the $ManagementPack variable.

The next three commands get templates by using the Get-SCSMObjectTemplate cmdlet.
The commands store these templates in the $Template01, $Template02, and $Template01 variables.
The first two templates are used in the values of the *Notification* parameter.
The other template is used as the value of the *Template* parameter.

The fourth command creates a DCM workflow that has the name DCMWorkflow03.

The final command verifies the creation by using the Get-SCSMDCMWorkflow cmdlet.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

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

### -ConfigurationBaseLine
Specifies the hash table that represents the baseline configuration for the DCM workflow.
Valid values are: 

- Baseline 
- Configuration

```yaml
Type: Hashtable[]
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

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

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

### -Description
Specifies the description of the DCM workflow.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the workflow object that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates whether this cmdlet enables or disables the DCM workflow.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNotification
Indicates whether this cmdlet enables or disables notifications.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementPack
Specifies the management pack in which the DCM workflow is stored.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Notification
Specifies the notification details of the DCM workflow.

```yaml
Type: Hashtable[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the DCM workflow that it creates.
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

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

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

### -Template
Specifies the Object template to apply to the DCM workflow.

```yaml
Type: ManagementPackObjectTemplate
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMDCMWorkflow.md)

[Remove-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMDCMWorkflow.md)

[Update-SCSMDCMWorkflow](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMDCMWorkflow.md)

