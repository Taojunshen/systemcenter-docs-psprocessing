---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: EE0CFB3C-9D0B-4D6A-886A-C98D3CEFECC8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Import-SCSMInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Import-SCSMInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Import-SCSMInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Import-SCSMInstance

## SYNOPSIS
Imports objects and relationships from a .csv file into Service Manager.

## SYNTAX

```
Import-SCSMInstance -FormatFileName <String> -DataFileName <String> [-BatchSize <Int32>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCSMInstance** cmdlet imports objects and relationships from a comma-separated value (.csv) file into Service Manager.

Two parameters must be set to import instances in bulk into Service Manager: 

- *DataFileName*, which must contain the file path of a .csv file that contains the instance data. 
- *FormatFileName*, which must contain the file path of an .xml file that defines the format of the .csv file.

The optional *BatchSize* parameter specifies the number of objects or projection instances that will be committed on each database write.

## EXAMPLES

### Example 1: Import computer projections
```
PS C:\>Import-SCSMInstance -FormatFileName "computers.xml" -DataFileName "computers.csv" -BatchSize 100
Contents of computers.xml
-------------------------
<CSVImportFormat>
  <Projection Type="Microsoft.Windows.Computer.ProjectionType">
    <Seed>
      <Class Type="Microsoft.Windows.Server.Computer">
        <Property ID="IsVirtualNode"/>
        <Property ID="PrincipalName"/>
      </Class>
    </Seed>
    <Component Alias="OperatingSystem">
      <Seed>
        <Class Type="Microsoft.Windows.OperatingSystem">
          <Property ID="OSVersion"/>
          <Property ID="ProductType"/>
          <Property ID="BuildNumber"/>
        </Class>
      </Seed>
    </Component>
  </Projection>
</CSVImportFormat>
Contents of computers.csv
-------------------------
false, computer1, 6.1, Windows, 1003
false, computer2, 6.1, Windows, 1003
```

This command imports computer projections from the file that is named computers.csv.
The command imports 100 rows at a time.

## PARAMETERS

### -BatchSize
Specifies the number of objects or projection instances that this cmdlet commits on each database write.
This value must be an integer between 1 and 5000.
The default value is 50.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 50
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

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

### -DataFileName
Specifies the file path of the .csv file that contains the instance data.

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

### -FormatFileName
Specifies the file path of an .xml file in which the format of the .csv file is defined.

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

