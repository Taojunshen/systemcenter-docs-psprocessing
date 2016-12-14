---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225396
schema: 2.0.0
ms.assetid: E89A48C4-E884-438A-BF5C-4861B0B0C5CB
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Import-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Import-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/Import-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SCSMManagementPack

## SYNOPSIS
Imports management packs.

## SYNTAX

### FromManagementPackFile (Default)
```
Import-SCSMManagementPack [-Fullname] <String[]> [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromManagementPack
```
Import-SCSMManagementPack [-ManagementPack] <ManagementPack[]> [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCSMManagementPack** cmdlet imports management packs.

Service Manager attempts to validate the XML code of the management packs before the import.
If the management pack contains XML code that is not valid, the management pack is not imported and an error is returned.

## EXAMPLES

### Example 1: Import a management pack file
```
PS C:\>Import-SCSMManagementPack "c:\temp\contosomanagementpack.xml"
```

This command imports the management pack file c:\temp\contosomanagementpack.xml.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

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
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.
The default value is the current user.

You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: User account of the current context.
Accept pipeline input: False
Accept wildcard characters: False
```

### -Fullname
Specifies the full path and file names of the management packs to import.
The list must contain files that are management packs (*.xml, *.mp) or management pack bundles (*.mpb).
If you specify a management pack bundle, all management packs from that bundle are imported.

```yaml
Type: String[]
Parameter Sets: FromManagementPackFile
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagementPack
Specifies one or more management packs to import.
You can enter a **ManagementPack** object that is returned by the **Get-SCManagementPack** cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Passes the newly imported management pack to the pipeline.
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

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the **Get-SCManagementGroupConnection** cmdlet.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
You can pipe a management pack to the *ManagementPack* parameter of the **Import-SCSMManagementPack** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
An object that represents the management pack.
It is available only when you use the *PassThru* parameter.

## NOTES
* If you specify multiple management packs, the order in which those management packs are imported will satisfy management pack interdependencies. As a result, management packs might be imported in an order that differs from the order that is provided at the command prompt.

  

## RELATED LINKS

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Export-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Protect-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Test-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/New-SCSMManagementPackBundle.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Remove-SCSMManagementPack.md)

