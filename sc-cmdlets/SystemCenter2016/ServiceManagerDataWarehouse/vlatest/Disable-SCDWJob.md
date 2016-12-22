---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C74DF5D2-0E3C-4C7D-80ED-65DADD918E2C
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Disable-SCDWJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Disable-SCDWJob

## SYNOPSIS
Disables a data warehouse job to prevent it from running in the future.

## SYNTAX

```
Disable-SCDWJob [-JobName] <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Disable-SCDWJob** cmdlet disables a job, which prevents it from running in the future.
When a job is disabled, any remaining modules that have not run yet will complete.
After the job completes its current run, it will not run according to its specified schedule and you cannot run it manually.

To re-enable a disabled job, use the **Enable-SCDWJob** cmdlet.

## EXAMPLES

### Example 1: Disable a job
```
PS C:\>Disable-SCDWJob -JobName "Extract_Contoso" â€"ComputerName "serverDW72"
```

This command disables the `Extract_Contoso` job.

### Example 2: List jobs that are enabled
```
PS C:\>Get-SCDWJob -ComputerName "serverDW72" | Sort-Object -Property IsEnabled,Name | Format-Table -Property Name,IsEnabled -AutoSize
```

This command lists the jobs according to their **IsEnabled** state.

### Example 3: Disable all jobs
```
PS C:\>$creduser12 = Get-Credential
PS C:\>Get-SCDWJob -ComputerName "serverDW72" -credential $creduser12 | ForEach-Object {$_.DisableJob()}
```

The first command obtains user credentials to store in a variable for the *Credential* parameter.

The second command disables all the jobs using the **ForEach-Object** cmdlet and the specified credentials.

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
Specifies the Data Warehouse job to disable.
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

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

[Enable-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md)

[Start-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md)

