---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 5A13730B-08B7-44FA-A0F7-06CF1CA98DB6
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMConnector

## SYNOPSIS
Retrieves connectors that are defined in Service Manager.

## SYNTAX

### Empty (Default)
```
Get-SCSMConnector [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromEMODisplayNameParameterSetName
```
Get-SCSMConnector [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMONameParameterSetName
```
Get-SCSMConnector [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMOIdParameterSetName
```
Get-SCSMConnector [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMConnector** cmdlet retrieves connectors that are defined in Service Manager.
If you do not specify the *Name* parameter, this cmdlet gets all connectors.
For each returned connector, the cmdlet displays type, name, and status information.

## EXAMPLES

### Example 1: Get all connectors
```
C:\PS>Get-SCSMConnector
Enabled              DisplayName            DataProviderName
-------              -----------            ----------------
False                SCSM Connector         SmsConnector
True                 AD Connector           ADConnector
False                AD Connector 2         ADConnector
```

This command retrieves all connectors and for each connector displays its status, display name, and its data provider.

### Example 2: Get a specific connector
```
C:\PS>Get-SCSMConnector -DisplayName "SCSM*"
Enabled  DisplayName        DataProviderName
-------  -----------        ----------------
False    SCSM Connector     SmsConnector
```

This command retrieves all connectors whose *DisplayName* matches the string SCSM.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the Service Manager SDK Service runs.
The user account that is defined in the *Credential* parameter must have access rights to the specified computer.

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

### -Credential
Represents a user with the credentials to interact with Service Manager.
If not properly specified, the cmdlet returns a terminating error.

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
Specifies the display name of the connector to retrieve.

```yaml
Type: String[]
Parameter Sets: FromEMODisplayNameParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the connector to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromEMOIdParameterSetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the connector to retrieve.
You can specify a regular expression.

```yaml
Type: String[]
Parameter Sets: FromEMONameParameterSetName
Aliases: 

Required: True
Position: 0
Default value: .*
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe a name to the *Name* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Connectors.ADConnector
This cmdlet retrieves connector objects that include the information that describes each connector and its properties.

## NOTES

## RELATED LINKS

[Remove-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMConnector.md)

[Start-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Start-SCSMConnector.md)

[Update-SCSMConnector](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMConnector.md)

