---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 542D9143-BE81-42C7-89D7-E0FD66DCD7E2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Register-SCDWSource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Register-SCDWSource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Register-SCDWSource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Register-SCDWSource

## SYNOPSIS
Registers instances of data source types to the data warehouse.

## SYNTAX

```
Register-SCDWSource [-AdditionalData <Object>] [-DataSourceTypeName] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] -DataSourceName <String> [-Properties <Hashtable>]
 [-FullPathToSourceManagementPackBundle <String>] [[-SourceComputerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Register-SCDWSource** cmdlet registers instances of data source types, such as Service Manager, Operations Manager, and Configuration Manager, to the data warehouse.

## EXAMPLES

### Example 1: Register a Service Manager management group
```
PS C:\>$CredUser1 = Get-Credential
PS C:\> Register-SCDWSource -ComputerName "serverDW72" -DataSourceTypeName "ServiceManager" -SourceComputerName "serverDW72" -Credential $CredUser1
```

The first command prompts for your credentials and stores them in an object variable.

The second command registers a Service Manager management group to the data warehouse.

### Example 2: Register an Operations Manager management group
```
PS C:\>$CredUser1 = Get-Credential
PS C:\>Register-SCDWSource -ComputerName "serverDW72" -DataSourceTypeName "OperationsManager" -SourceComputerName "om2012" -DataSourceDbName "OperationsManager" -DataSourceDbServerName "om2012" -FullPathToSourceManagementPackBundle "C:\Program Files\Microsoft System Center\Service Manager 2012\OperationsManagerMP.mpb" -Credential $CredUser1
```

The first command prompts for your credentials and stores them in an object variable.

The second command registers an Operations Manager management group with the data warehouse.

### Example 3: Register a Configuration Manager server
```
PS C:\>Register-SCDWSource -ComputerName "serverDW72" -DataSourceType "ConfigurationManager.DataSource" -DataSourceName "serverDW72_sms_smq-SCCMDataSource" -Properties @{ ServerName = 'serverDW72'; DatabaseName = 'sms_smq'; SubjectList = 'Microsoft.EnterpriseManagement.ServiceManager.Connector.Sms,Microsoft.SystemCenter.ConfigurationManager.Connector.PowerManagement'; SecureReferenceId = 'bb89ca43-3e64-07fc-a136-592183066184'; Version='bd3bc1fe-1546-5108-2faf-4d5c01d2bc6a' } -FullPathToSourceManagementPackBundle "C:\Program Files\Microsoft System Center\Service Manager 2012\SCCMDW.mpb" -AdditionalData @($input)[0]
```

This command registers a Configuration Manager server with the data warehouse.

## PARAMETERS

### -AdditionalData
Specifies any additional data that a particular source might have to send during registration.
For example, during a Configuration Manager source registration, this parameter provides the necessary credentials in the form of a credential object, which the Configuration Manager source uses to contact the Configuration Manager server.

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
Specifies the name of the data warehouse management server on which to run the **Register-SCDWSource** cmdlet.
The user account specified in the *Credential* parameter must have access rights to the specified computer.
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
The provided user account must have access to that server.

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

### -DataSourceTypeName
Specifies the type of the data source.
You can use the **Get-SCDWSourceType** cmdlet to retrieve **TypeNames**.

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

### -SourceComputerName
Specifies the name of the Service Manager management server that is to be registered with the data warehouse.

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

### -DataSourceName
{{Fill DataSourceName Description}}

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

### -FullPathToSourceManagementPackBundle
{{Fill FullPathToSourceManagementPackBundle Description}}

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
{{Fill Properties Description}}

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

[Enable-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWSource.md)

[Disable-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWSource.md)

[Get-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWSource.md)

[Set-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Set-SCDWSource.md)

[Unregister-SCDWSource](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Unregister-SCDWSource.md)

