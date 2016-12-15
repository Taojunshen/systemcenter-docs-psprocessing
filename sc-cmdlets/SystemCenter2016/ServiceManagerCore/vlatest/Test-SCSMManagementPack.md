---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225419
schema: 2.0.0
ms.assetid: 98E3F10B-F4A3-4969-963E-489FAB8D0842
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCSMManagementPack

## SYNOPSIS
Tests the validity of a management pack.

## SYNTAX

```
Test-SCSMManagementPack [-FullName] <String> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCSMManagementPack** cmdlet tests the validity of a management pack.
This cmdlet replaces the MPVerify.exe utility, which verifies a management pack by using the software development kit (SDK) method **ManagementPack.Verify()**.
This cmdlet requires that the user specify the path to the management pack file and the name of the computer to use for resolving dependencies.
For management pack bundle files (.mpb), all the management packs in the bundle will be tested for validity.

All issues that are found during the test are written as nonterminating errors, one error per issue.
The output of the cmdlet is an object consisting of the management pack name, the path of the management pack, and a property named **Verified**, which equals **True** if no errors are found and **False** if errors were found.

## EXAMPLES

### Example 1: Test a management pack
```
PS C:\>$MpError = Test-SCSMManagementPack "C:\temp\TestingMP.xml"
PS C:\>$MpError | Format-List
Verified : False

Name     : 

FullName : C:\temp\TestingMP.xml

Error    : XSD verification failed for the management pack. [Line: 29, Position: 8]
```

These commands test the TestingMP.xml management pack.

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
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullName
Specifies the full name and path of the management pack.
The management pack can be a sealed, unsealed, or bundled management pack.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the **Get-SCSMManagementGroupConnection** cmdlet.

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
You can send a management pack full name to the *FullName* parameter of the **Test-SCSMManagementPack** cmdlet by using the pipeline operator.
The *FullName* parameter accepts **propertyname** values, which are the output of **Get-ChildItem** and of any other commands that produce **System.IO.FileInfo** objects.

## OUTPUTS

### Microsoft.SystemCenter.Core.Commands.ManagementPackVerificationResult
An object that represents a management pack verification result.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Import-SCSMManagementPack.md)

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Export-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementPack.md)

