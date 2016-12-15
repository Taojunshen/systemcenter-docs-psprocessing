---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Enable-SCDWSource.md
schema: 2.0.0
ms.assetid: 282D1F02-ED1E-41E2-BE96-7896BC457491
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Set-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Set-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/vlatest/Set-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCDWSource

## SYNOPSIS
Sets the definition of classes and relationships that can be populated for an instance of a data source.

## SYNTAX

```
Set-SCDWSource [-Properties <Hashtable>] [-FullPathToSourceManagementPackBundle <String>]
 [-AdditionalData <Object>] [-DataSourceTypeName] <String> [-DataSourceName] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCDWSource** cmdlet updates the definition of classes and relationships that can be populated for an instance of a data source.

## EXAMPLES

### Example 1: Set properties for a data source
```
PS C:\>$cred = Get-Credential
PS C:\>Set-SCDWSource -DataSourceType "ConfigurationManager.DataSource"  -DataSourceName "MSITData" -Properties @{ Version="D0925349-F1FC-1084-0761-EE60D21B1141"; SyncType="9BFF3B4B-80D0-A263-2DAD-90A67C5FCA39"}  -AdditionalData $cred  -FullPathToSourceManagementPackBundle "C:\NewCMSourceMPS.mpb" -ComputerName "serverDW72"
```

The first command prompts for user credentials and stores them in a variable.

The second command updates the `version` and the `synctype` properties for a Configuration Manager data source.

## PARAMETERS

### -AdditionalData
Specifies any additional data that a particular source has to send during registration.
Specifically, this is used during a **cmshort** source registration, to provide credentials in the form of a credential object that the **cmshort** source uses to contact the **cmshort** server.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the *Credential* parameter must have access rights to the specified computer.
You can omit this parameter only if the System Center Data Access Service is running on the same computer that has Service Manager installed.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use when you are connecting to the server on which the System Center Data Access service is running.
The user account that is provided must have access to that server.

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

### -DataSourceName
Specifies the name of the data source to use.
You can use the **Get-SCDWSource** cmdlet to retrieve names of registered data sources.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataSourceTypeName
Specifies the type of the data source.
You can use the **Get-SCDWSourceType** cmdlet to retrieve data source type names.

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

### -FullPathToSourceManagementPackBundle
Specifies the path to the management pack bundle that contains the management packs with the definitions for the new source types.
This makes it possible for you to define the type system for the new source in the same manner that type systems are defined in management packs by declaring classes.

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

### -Properties
Specifies further arguments that will be used when a data source is set up.
The hashtable contents vary according to the data source type.

```yaml
Type: Hashtable
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Enable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/vlatest/Enable-SCDWSource.md)

[Disable-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/vlatest/Disable-SCDWSource.md)

[Get-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/vlatest/Get-SCDWSource.md)

[Register-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/vlatest/Register-SCDWSource.md)

[Unregister-SCDWSource](xref:SystemCenter2016/ServiceManagerData Warehouse/vlatest/Unregister-SCDWSource.md)

