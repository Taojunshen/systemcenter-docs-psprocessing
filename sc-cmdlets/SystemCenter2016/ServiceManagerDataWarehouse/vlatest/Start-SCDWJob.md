---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Disable-SCDWJob.md
schema: 2.0.0
ms.assetid: F26FC623-F052-422E-9F5D-CDAAAA5C5C45
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCDWJob

## SYNOPSIS
Starts a data warehouse job.

## SYNTAX

```
Start-SCDWJob -JobName <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCDWJob** cmdlet starts a data warehouse job.
When a job is started, its associated job modules run in the order that the job sets.
To stop a job, use the **Stop-SCDWJob** cmdlet.

## EXAMPLES

### Example 1: Start a job
```
PS C:\>Start-SCDWJob â€"ComputerName "serverDW72" -JobName "Extract_Contoso"
```

This command starts the `Extract_Contoso` job.

## PARAMETERS

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

### -JobName
Specifies the job to be started.
The **JobName** parameter is mandatory.

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

[Disable-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJob.md)

[Enable-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md)

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

[Stop-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Stop-SCDWJob.md)

