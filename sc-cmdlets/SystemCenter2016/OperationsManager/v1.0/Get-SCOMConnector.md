---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187708
schema: 2.0.0
ms.assetid: 7089AD4F-92B9-48D2-8A35-91D7F58B89EE
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMConnector.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMConnector.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMConnector.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMConnector

## SYNOPSIS
Gets  Operations Manager connectors.

## SYNTAX

### Empty (Default)
```
Get-SCOMConnector [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromConnectorDisplayName
```
Get-SCOMConnector [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromConnectorId
```
Get-SCOMConnector [-Id <Guid[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromConnectorName
```
Get-SCOMConnector [-Name <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMConnector** cmdlet gets one or more configuration item (CI) connectors for System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Get connectors by using a display name
```
PS C:\>Get-SCOMConnector -DisplayName "Connector*"
```

This command gets all connectors that have a display name that begins with Connector.

### Example 2: Get connectors by using a name
```
PS C:\>Get-SCOMConnector -Name "Operations Manager*"
```

This command gets all connectors that have a name that begins with Operations Manager.

### Example 3: Get a connector by using an Id
```
PS C:\>Get-SCOMConnector -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the connector that has the Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
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

### -DisplayName
Specifies the display name of the connector.
Values for this parameter depend on which localized management packs you import and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromConnectorDisplayName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies an array of GUIDs of connectors.
To get the Id of a connector, type `Get-SCOMConnector | Format-Table Name, Id`.

```yaml
Type: Guid[]
Parameter Sets: FromConnectorId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names of connectors.

```yaml
Type: String[]
Parameter Sets: FromConnectorName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

A connection object represents a connection to a management server.
The default is the current management group connection.

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

[Add-SCOMConnector](xref:SystemCenter2016/OperationsManager/v1.0/Add-SCOMConnector.md)

[Remove-SCOMConnector](xref:SystemCenter2016/OperationsManager/v1.0/Remove-SCOMConnector.md)

