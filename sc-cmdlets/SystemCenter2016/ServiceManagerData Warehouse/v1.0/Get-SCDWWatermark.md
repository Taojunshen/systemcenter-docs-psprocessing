---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: a3467fe7-f0e7-41fd-9453-0b01c43f122d
schema: 2.0.0
ms.assetid: 1C934679-7D5A-4093-B177-88BFE0D9C053
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWWatermark.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWWatermark.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManagerData%20Warehouse/v1.0/Get-SCDWWatermark.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDWWatermark

## SYNOPSIS
Gets the latest watermark for a job module.

## SYNTAX

```
Get-SCDWWatermark [-ModuleType] <String> [-ModuleName] <String> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCDWWatermark** cmdlet gets the stage of completion of the specified module, along with any other modules that the current module depends on. 
Modules depend on each other, and every job module processes data incrementally.
This cmdlet provides a complete picture of data latency.

## EXAMPLES

### Example 1: Get module watermarks
```
PS C:\>Get-SCDWWatermark -ComputerName "serverDW72" -ModuleType "Transform" -ModuleName "TransformSoftwareUpdateDim"
```

This command gets the watermarks for a specified module and module name.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
The user account that is defined in the **Credential** parameter must have access rights to the specified computer.
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

### -ModuleName
Specifies the name of the job module for which to retrieve the watermark.
You can use the **Get-SCDWJobModule** cmdlet to retrieve the job module.
Only modules that start with either Transform or Load will be retrieved.

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

### -ModuleType
Specifies the type of job module for which to retrieve the watermark.
Valid strings are Transform and Load.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Warehouse.Cmdlets.GetSCDWWatermark

## NOTES

## RELATED LINKS

