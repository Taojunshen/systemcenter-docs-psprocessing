---
external help file: Microsoft.EnterpriseManagement.Warehouse.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 95E2A68C-A4BF-4F73-A70F-C4CDF6426348
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Stop-SCDWJob.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Stop-SCDWJob.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Stop-SCDWJob.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-SCDWJob

## SYNOPSIS
Stops a data warehouse job.

## SYNTAX

```
Stop-SCDWJob [-JobName] <String> [-ComputerName <String>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SCDWJob** cmdlet stops a data warehouse job.
Job modules that are currently running complete gracefully, and the rest of the job modules that have not run yet queue up.

## EXAMPLES

### Example 1: Stop a job
```
PS C:\>Stop-SCDWJob â€"ComputerName "serverDW72" -JobName "Extract_Contoso"
```

This command stops the `Extract_Contoso` job.

### Example 2: Stop all jobs that are not already stopped
```
PS C:\>$cred = Get-Credential
PS C:\>Get-SCDWJob -ComputerName "serverDW72" â€"Credential $cred | ForEach-Object {
>> if ($_.Status -ne "Stopped") {
>> Stop-SCDWJob -ComputerName "IXSMTestDW" -JobName $_.Name
>> }
>> }
```

The first command prompts for user credentials and stores them in a variable.

The second command stops all jobs that do not have the status of stopped.

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
Specifies the job to be stopped.
The **JobName** parameter is mandatory.

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

[Enable-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Enable-SCDWJob.md)

[Get-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Get-SCDWJob.md)

[Start-SCDWJob](xref:SystemCenter2016/ServiceManagerDataWarehouse/vlatest/Start-SCDWJob.md)

