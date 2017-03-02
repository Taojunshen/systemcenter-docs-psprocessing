---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C766C272-8930-4D87-88B6-F8B229F4097A
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCOMAlertConnector

## SYNOPSIS
Creates an Operations Manager alert connector in Service Manager.

## SYNTAX

```
New-SCOMAlertConnector [-CloseAlert] [[-Description] <String>] [-Enable <Boolean>] [-DisplayName] <String>
 -OperationsManagerServer <String> [-PassThru] [-ResolveIncident] [-Rules <AlertRule[]>]
 [-RunAsAccount <ManagementPackSecureReference>] [-PollIntervalInSeconds <Int32>]
 [-Template <ManagementPackObjectTemplate>] [-SyncNow] -SCOMCredential <PSCredential>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCOMAlertConnector** cmdlet creates an Operations Manager alert connector in Service Manager.

## EXAMPLES

### Example 1: Create an Operations Manager alert connector
```
PS C:\>$RunAsAccount = Get-SCSMRunAsAccount -UserName "AdminRA"
PS C:\> $Credential = Get-Credential
PS C:\> New-SCOMAlertConnector -DisplayName "SCOM ALERT CONNECTOR" -OperationsManagerServer "server.contoso.com" -SCOMCredential $Credential -RunAsAccount $RunAsAccount
```

The first command gets a Run As account for AdminRA by using the Get-SCSMRunAsAccount cmdlet.
The command stores the result in the $RunAsAccount variable.

The second command prompts you for credentials by using the Get-Credential cmdlet, and then stores the credentials in the $Credential variable.

The final command creates an Operations Manager alert connector which has no rules, and which uses a default template.

## PARAMETERS

### -CloseAlert
Specifies that Operations Manager closes alerts after they are resolved or closed in Service Manager.

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

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
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
Specifies a description for the connector.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the name of the connector.

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
Indicates whether this cmdlet enables or disables the connector.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### -OperationsManagerServer
Specifies the name of the Operations Manager server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the Operations Manager alert connector that it creates.
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

### -PollIntervalInSeconds
Specifies the polling interval, in seconds, for the Operations Manager alert connector.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResolveIncident
Specifies that this cmdlet configures Service Manager to automatically resolve incidents after Operations Manager closes the associated alert.

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

### -Rules
Specifies the rules which provide routing instructions for the alerts.
The rules which provide routing instructions for the alerts.

```yaml
Type: AlertRule[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies the Run As account to use during connector synchronization.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Operational System Account
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCOMCredential
Specifies the credential to use when connecting to Operations Manager.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents a session to a Service Manager management server.

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

### -SyncNow
Starts a synchronization of the Operations Manager alert connector.

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

### -Template
Specifies the default template to use when an alert does not match a rule.

```yaml
Type: ManagementPackObjectTemplate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Operations Manager Incident Template
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

[New-SCADConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md)

[New-SCCMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md)

[New-SCOMConfigurationItemConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md)

[New-SCOrchestratorConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOrchestratorConnector.md)

[New-SCVMMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md)

