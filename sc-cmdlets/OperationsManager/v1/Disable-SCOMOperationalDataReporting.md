---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239467
schema: 2.0.0
ms.assetid: 16C66473-BD5A-4A0B-BA08-E5EF4F64925A
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Disable-SCOMOperationalDataReporting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Disable-SCOMOperationalDataReporting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Disable-SCOMOperationalDataReporting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCOMOperationalDataReporting

## SYNOPSIS
Disables operational data reporting for the management group.

## SYNTAX

```
Disable-SCOMOperationalDataReporting [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCOMOperationalDataReporting** cmdlet disables operational data reporting for the management group in System Center 2016 - Operations Manager.

## EXAMPLES

### Example 1: Disable data reporting
```
PS C:\>Disable-SCOMOperationalDataReporting
```

This command disables operational data reporting.

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
Specifies a **PSCredential** object for the management group connection.
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-SCOMOperationalDataReporting](xref:OperationsManager/v1/Enable-SCOMOperationalDataReporting.md)

[Test-SCOMOperationalDataReporting](xref:OperationsManager/v1/Test-SCOMOperationalDataReporting.md)

