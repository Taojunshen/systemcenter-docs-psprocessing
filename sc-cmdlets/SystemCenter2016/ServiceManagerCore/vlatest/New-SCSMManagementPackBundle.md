---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4D47BC7D-2800-4DC6-BD09-56C80547A946
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMManagementPackBundle

## SYNOPSIS
Creates a management pack bundle.

## SYNTAX

```
New-SCSMManagementPackBundle [-Name] <String> [-ManagementPack] <String[]> [[-Resource] <String[]>] [-Force]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMManagementPackBundle** cmdlet bundles individual management packs and their resources together to createa management pack bundle.

## EXAMPLES

### Example 1: Create a management pack bundle with no resources
```
PS C:\>$MpbPath = "Resources\GroupQueueMP.xml"
PS C:\>New-SCSMManagementPackBundle -Name ContosoPack17.mpb -ManagementPack $MpbPath
```

This command creates a management pack bundle from a management pack that has no resources.

### Example 2: Create a management pack bundle with resources
```
PS C:\>$MpbPath = "ContosoPack72.mpb"
PS C:\>$Mp2 = "Resources\DeviceProjectionMP.mp"
PS C:\>$Mp1 = "Resources\GroupQueueMP.xml"
PS C:\>$Mp3 = "Resources\ResourceMP.xml"
PS C:\>$Resource = "Resources\LinkingFrameworkUnitTest.dll"
PS C:\>New-SCSMManagementPackBundle -Name $MpbPath -ManagementPack $Mp1, $Mp2, $Mp3 -Resource $Resource
```

This command creates a management pack bundle from a management pack that has resources.

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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

This ensures that a new management pack bundle file is created even if one already exists in the location that is specified in the *Name* parameter.

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

### -ManagementPack
Specifies one or more management packs to be included in the new management pack bundle.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the file path and the file name of the management pack bundle.
The file extension must be mpb, for example, folder1\file2.mpb.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Resource
Specifies the resources that are required by the management packs in the bundle.
These resources are added into the management pack bundle.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
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

###  
You cannot pipe input to this cmdlet.

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Import-SCSMManagementPack.md)

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Export-SCSMManagementPack.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementPack.md)

