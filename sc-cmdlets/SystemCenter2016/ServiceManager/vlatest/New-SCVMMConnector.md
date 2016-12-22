---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C246BFD0-9149-4947-98C3-688178A2817D
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/New-SCVMMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMMConnector

## SYNOPSIS
Creates a Service Manager Virtual Machine Manager connector.

## SYNTAX

```
New-SCVMMConnector [[-Description] <String>] [-Enable <Boolean>] [-DisplayName] <String> [-PassThru]
 [[-RunAsAccount] <ManagementPackSecureReference>] [-ServerName] <String> [[-ServerPort] <Int32>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMMConnector** cmdlet creates a Service Manager Virtual Machine Manager connector.

## EXAMPLES

### Example 1: Create a Virtual Machine Manager connector
```
PS C:\>New-SCVMMConnector -DisplayName "contoso-vmm" -ServerName "ContosoServer.net"
```

This command creates a Virtual Machine Manager connector.

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
Specifies the display name of the connector.

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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that this cmdlet returns the Virtual Machine Manager connector that it creates.
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

### -RunAsAccount
Specifies the Run As account that the connector uses when it runs.

```yaml
Type: ManagementPackSecureReference
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
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

### -ServerName
Specifies the Virtual Machine Manager server name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerPort
{{Fill ServerPort Description}}

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

## OUTPUTS

## NOTES

## RELATED LINKS

[New-SCADConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCADConnector.md)

[New-SCCMConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCCMConnector.md)

[New-SCOMAlertConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMAlertConnector.md)

[New-SCOMConfigurationItemConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOMConfigurationItemConnector.md)

[New-SCOrchestratorConnector](xref:SystemCenter2016/ServiceManager/vlatest/New-SCOrchestratorConnector.md)

