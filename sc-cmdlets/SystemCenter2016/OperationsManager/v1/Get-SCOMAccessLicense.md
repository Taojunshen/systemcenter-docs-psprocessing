---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=221569
schema: 2.0.0
ms.assetid: 08C5E068-68A1-4F3B-9CD5-BFFF5F3D5C81
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMAccessLicense.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMAccessLicense.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Get-SCOMAccessLicense.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMAccessLicense

## SYNOPSIS
Gets information about licenses for Operations Manager and Windows.

## SYNTAX

### Empty (Default)
```
Get-SCOMAccessLicense [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromLicense
```
Get-SCOMAccessLicense [-ShowLicense] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromLicenseName
```
Get-SCOMAccessLicense [-LicenseName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMAccessLicense** cmdlet gets a list of System Center 2016 - Operations Manager license types or a list of computers and their license information.
Use this cmdlet as part of a central management system that correlates and deduplicates the license information with Access License data from other System Center 2016 products.

## EXAMPLES

### Example 1: Get all licenses on the local computer
```
PS C:\>Get-SCOMAccessLicense
```

This command gets information about all licenses for System Center 2016 - Operations Manager and Windows for the local computer.

### Example 2: Get all licenses for Operations Manager
```
PS C:\>Get-SCOMAccessLicense -LicenseName
```

This command gets all the licenses for System Center 2016 - Operations Manager for the local computer.

### Example 3: Get licenses by using a name
```
PS C:\>Get-SCOMAccessLicense -LicenseName "System Center Operations Manager 2012 Management Server"
```

This command gets all licenses that have the name System Center Operations Manager 2012 Management Server.

### Example 4: Get licenses by using a name
```
PS C:\>Get-SCOMAccessLicense -LicenseName "SML"
```

This command gets all licenses that have the name SML.

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

### -LicenseName
Specifies an array of license names.

```yaml
Type: String[]
Parameter Sets: FromLicenseName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

### -ShowLicense
Indicates that the cmdlet returns a list of available licenses that apply to this product.

```yaml
Type: SwitchParameter
Parameter Sets: FromLicense
Aliases: List

Required: True
Position: 1
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

[Get-SCOMLicense](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMLicense.md)

[Set-SCOMLicense](xref:SystemCenter2016/OperationsManager/v1/Set-SCOMLicense.md)

