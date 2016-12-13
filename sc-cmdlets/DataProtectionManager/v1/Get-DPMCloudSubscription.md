---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Set-DPMCloudSubscriptionSetting.md
schema: 2.0.0
ms.assetid: 3C91989A-112B-46C8-8E77-1D265260DF33
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMCloudSubscription.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMCloudSubscription.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Get-DPMCloudSubscription.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMCloudSubscription

## SYNOPSIS
Gets an Azure Online Backup subscription object.

## SYNTAX

```
Get-DPMCloudSubscription [[-DPMServerName] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMCloudSubscription** cmdlet gets a Windows Azure Online Backup subscription object in System Center 2016 - Data Protection Manager (DPM).

## EXAMPLES

### Example 1: Return status of an Azure Online Backup subscription
```
PS C:\>Get-DPMCloudSubscription -DPMServerName "TestingServer"
```

This command returns the Azure Online Backup subscription status for the DPM server named TestingServer.

## PARAMETERS

### -DPMServerName
Specifies the name of the DPM server on which this cmdlet acts.

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

[Set-DPMCloudSubscriptionSetting](xref:DataProtectionManager/v1/Set-DPMCloudSubscriptionSetting.md)

[Data Protection Manager Cmdlets](xref:DataProtectionManager/v1/DataProtectionManager.md)

