---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 90d587fa-3d33-4328-b6c0-f22d1087488f
schema: 2.0.0
ms.assetid: 0F06A364-D7EA-4E32-B4B1-C3C75A017A81
updated_at: 12/20/2016 4:46 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkServiceCertificateUrl.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkServiceCertificateUrl.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/94a19c388d35167727d61daa8d59367c5c24c63e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkServiceCertificateUrl.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCNetworkServiceCertificateUrl

## SYNOPSIS
Gets the URL for a network service certificate.

## SYNTAX

```
Get-SCNetworkServiceCertificateUrl -ConnectionString <String> -ConfigurationProvider <ConfigurationProvider>
 -RunAsAccount <RunAsAccount> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNetworkServiceCertificateUrl** cmdlet gets the URL for a network service certificate.

## EXAMPLES


## PARAMETERS

### -ConfigurationProvider
Specifies a configuration provider object.

A configuration provider is a plug-in to Virtual Machine Manager (VMM) that translates VMM PowerShell commands to API calls that are specific to a type of load balancer.
If no configuration provider is specified, VMM uses the Manufacturer and Model information to choose an available configuration provider.
If no configuration provider is found, the load balancer will not be added.

```yaml
Type: ConfigurationProvider
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionString
Specifies the information required to connect to the virtual switch extension manager.

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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

