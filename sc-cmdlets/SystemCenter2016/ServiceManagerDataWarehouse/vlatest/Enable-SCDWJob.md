---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: ./Disable-SCDWJob.md
schema: 2.0.0
ms.assetid: 589E2B09-B771-4B5C-9F50-65AADD6D2B69
updated_at: 12/15/2016 6:30 PM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/59ca46449cbaf6c065d4887fdd68c8de98ef34f0/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Enable-SCDWJob

## SYNOPSIS
Enables a data warehouse job.

## SYNTAX

```
Enable-SCDWJob [-JobName] <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Enable-SCDWJob** cmdlet enables a data warehouse job, which allows it to run according to its specified schedule or to be started manually by using the **Start-SCDWJob** cmdlet.
To disable a job, use the **Disable-SCDWJob** cmdlet.

## EXAMPLES

### Example 1: Enable a job
```
PS C:\>Enable-SCDWJob -JobName Extract_Contoso â€"ComputerName "serverDW72"
```

This command enables the `Extract_Contoso` job.

### Example 2: List jobs and display job status
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" | Sort-Object -Property IsEnabled,Name | Format-Table -Property Name,IsEnabled -AutoSize
```

This command lists the jobs sorted by their **IsEnabled** value.

### Example 3: List disabled jobs
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" | Where-Object {$_.IsEnabled -eq $FALSE} | Sort-Object
-Property IsEnabled,Name | Format-Table -Property Name,IsEnabled -AutoSize
```

This command shows only the jobs that are disabled.

### Example 4: Enable jobs using credentials
```
PS C:\>$creduser1 = Get-Credential
PS C:\> Get-SCDWJob -ComputerName "serverDW72" -credential $creduser1 | ForEach-Object {$_.EnableJob()}
```

The first command stores user credentials in a variable for the *Credential* parameter.

The second command enables all the jobs using the **ForEach-Object** cmdlet.

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

### -JobName
Specifies the Data Warehouse job to enable.
The **JobName** parameter is a mandatory parameter.

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

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

[Start-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md)

[Stop-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Stop-SCDWJob.md)

