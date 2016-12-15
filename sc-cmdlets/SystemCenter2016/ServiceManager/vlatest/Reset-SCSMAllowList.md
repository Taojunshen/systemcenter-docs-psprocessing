---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225373
schema: 2.0.0
ms.assetid: A23D51BD-9244-4A2E-841D-047E00E70E6D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Reset-SCSMAllowList.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Reset-SCSMAllowList.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Reset-SCSMAllowList.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Reset-SCSMAllowList

## SYNOPSIS
Resets the allow list of classes that is used by the Operations Manager CI Connector in Service Manager to the default allow list.

## SYNTAX

```
Reset-SCSMAllowList [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Reset-SCSMAllowList** cmdlet resets the allow list of classes that the Operations Manager CI Connector in Service Manager uses to the default allow list.

The default allow list contains the following classes:

- **System.Service**. System.Library management pack
- **System.Database**. System.Library management pack
- **Microsoft.Windows.ApplicationComponent**. Microsoft.Windows.Library management pack
- **Microsoft.Windows.ComputerRole**. Microsoft.Windows.Library management pack
- **System.Computer**. System.Library management pack
- **System.OperatingSystem**. System.Library management pack
- **Microsoft.Windows.LogicalDevice**. Microsoft.Windows.Library management pack
- **System.SoftwareInstallation**. System.Library management pack
- **System.WebSite**. System.Library management pack

## EXAMPLES

### Example 1: Reset the allow list
```
PS C:\>Reset-SCSMAllowList
```

This command resets the allow list on the local server to the default allow list.

## PARAMETERS

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

[Add-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/vlatest/Add-SCSMAllowListClass.md)

[Get-SCSMAllowList](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMAllowList.md)

[Remove-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAllowListClass.md)

