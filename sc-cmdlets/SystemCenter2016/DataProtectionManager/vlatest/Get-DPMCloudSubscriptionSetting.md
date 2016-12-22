---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 90CB636A-2E2E-4291-9121-983BE693E0D2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscriptionSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscriptionSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscriptionSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMCloudSubscriptionSetting

## SYNOPSIS
Returns configuration settings for an Azure Online Backup subscription.

## SYNTAX

```
Get-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMCloudSubscriptionSetting** cmdlet returns configuration settings for a Windows Azure Online Backup subscription.

## EXAMPLES

### Example 1: Get configuration settings for an Azure Online Backup subscription
```
PS C:\>$Setting = Get-DPMCloudSubscriptionSetting -DPMServerName "TestingServer"
```

This command returns configuration settings for the Azure Online Backup subscription on the DPM server named TestingServer.

## PARAMETERS

### -DPMServerName
Specifies the name of the System Center 2016 - Data Protection Manager (DPM) server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName, CN

Required: False
Position: 1
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

[Get-DPMCloudSubscription](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscription.md)

[Set-DPMCloudSubscriptionSetting](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCloudSubscriptionSetting.md)

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

