---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225387
schema: 2.0.0
ms.assetid: B625A6BF-0526-48E5-81BE-2B141B2BF386
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Update-SCSMSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Update-SCSMSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/ServiceManager/v1.0/Update-SCSMSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCSMSetting

## SYNOPSIS
Updates the configuration settings for Service Manager.

## SYNTAX

```
Update-SCSMSetting [-Setting] <ISetting[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCSMSetting** cmdlet updates the configuration settings for Service Manager.

## EXAMPLES

### Example 1: Update activity settings
```
PS C:\>$Setting = Get-SCSMSetting -DisplayName "Activity"
PS C:\> $Setting.ManualActivityPrefix = "MA_"
PS C:\> Update-SCSMSetting -Setting $Setting
```

The first command gets the activity settings for Service Manager by using the Get-SCSMSetting cmdlet.
The command stores those settings in the $Setting variable.

The second command modifies the **ManualActivityPrefix** property of $Setting.

The final command updates the setting to have the current value of $Setting.

## PARAMETERS

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

### -PassThru
Indicates that this cmdlet returns the settings that it updates.
You can pass this object to other cmdlets.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Setting
Specifies an object which contains the updated settings for Service Manager.

```yaml
Type: ISetting[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.EnterpriseManagement.ServiceManager.Sdk.Settings.ISetting
You can pipe configuration settings to the *Settings* parameter.
You can use the Get-SCSMSetting cmdlet to retrieve a settings object.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMSetting](xref:SystemCenter2016/ServiceManager/v1.0/Get-SCSMSetting.md)

