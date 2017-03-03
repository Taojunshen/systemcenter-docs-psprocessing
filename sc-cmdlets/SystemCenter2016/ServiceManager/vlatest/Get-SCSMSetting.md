---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 2BDE34D9-908D-48B5-9A49-C9AE17085082
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMSetting

## SYNOPSIS
Retrieves configuration settings of System Center Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMSetting [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMSetting [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMSetting** cmdlet retrieves configuration settings of System Center Service Manager.

## EXAMPLES

### Example 1: Get configuration settings for the Problem feature
```
PS C:\>Get-SCSMSetting -DisplayName "Problem*"
DisplayName                        : Problem Settings
MaxAttachments                     : 10
MaxAttachmentSize                  : 64
PriorityMatrix                     : 
PriorityMaxValue                   : 
PriorityMinValue                   : 
ProblemIdPrefix                    : PR
Priority_UrgencyLowImpactHigh      : 
Priority_UrgencyLowImpactMedium    : 
Priority_UrgencyLowImpactLow       : 
Priority_UrgencyMediumImpactHigh   : 
Priority_UrgencyMediumImpactMedium : 
Priority_UrgencyMediumImpactLow    : 
Priority_UrgencyHighImpactHigh     : 
Priority_UrgencyHighImpactMedium   : 
Priority_UrgencyHighImpactLow      :
```

This command retrieves configuration settings for the Service Manager Problem feature.

### Example 2: Get configuration settings for the Data Retention feature
```
PS C:\>Get-SCSMSetting -DisplayName "*Retention*"
DisplayName       : Data Retention Settings
ChangeRequestDays : 365
IncidentDays      : 90
ProblemDays       : 365
HistoryDays       : 365
```

This command retrieves the configuration settings for the Service Manager Data Retention feature.

### Example 3: Get configuration settings for the Knowledge feature
```
PS C:\>Get-SCSMSetting -DisplayName "Knowledge*"
DisplayName   : Knowledge Management Settings
ArticlePrefix : KA
```

This command retrieves the configuration settings for the Service Manager Knowledge Managements feature.

### Example 4: Get configuration settings for the Change Request feature
```
PS C:\>("Change Request Settings" | Get-SCSMSetting ).__EnterpriseManagementObject.Id | Get-SCSMSetting
DisplayName                         : Change Request Settings
MaxFileAttachmentsCount             : 10
MaxFileAttachmentSizeinKB           : 64
SystemWorkItemChangeRequestIdPrefix : CR
```

This command retrieves the configuration settings for the Service Manager Change Request feature, using the GUID of solution settings.

### Example 5: Get configuration settings for the Activity Management feature
```
PS C:\>Get-SCSMSetting -DisplayName "Activity*"
DisplayName                                      : Activity Settings
SystemWorkItemActivityDependentActivityIdPrefix  : DA
SystemWorkItemActivityIdPrefix                   : AC
SystemWorkItemActivityManualActivityIdPrefix     : MA
SystemWorkItemActivityParallelActivityIdPrefix   : PA
SystemWorkItemActivityReviewActivityIdPrefix     : RA
SystemWorkItemActivitySequentialActivityIdPrefix : SA
```

This command retrieves the configuration settings for the Service Manager Activity Management feature.

### Example 6: Get configuration settings for the Incident Management feature
```
PS C:\>Get-SCSMSetting -DisplayName "Incident*"
DisplayName                        : Incident Settings
PrefixForId                        : IR
MaxAttachments                     : 10
MaxAttachmentSize                  : 2048
DefaultTierQueue                   : Tier 2
Priority_UrgencyLowImpactLow       : 1
Priority_UrgencyMediumImpactLow    : 2
Priority_UrgencyHighImpactLow      : 3
Priority_UrgencyLowImpactMedium    : 4
Priority_UrgencyMediumImpactMedium : 5
Priority_UrgencyHighImpactMedium   : 6
Priority_UrgencyLowImpactHigh      : 7
Priority_UrgencyMediumImpactHigh   : 8
Priority_UrgencyHighImpactHigh     : 9
Priority1ResolutionTime            : 1
Priority2ResolutionTime            : 2
Priority3ResolutionTime            : 3
Priority4ResolutionTime            : 4
Priority5ResolutionTime            : 5
Priority6ResolutionTime            : 6000
Priority7ResolutionTime            : 420
Priority8ResolutionTime            : 11520
Priority9ResolutionTime            : 90720
OpsMgrWebConsoleUrl                : 
SMTPDropFolder                     : smtp drop
SMTPBadFolder                      : smtp bad
MaximumEmailItems                  : 10
EmailProcesingIsEnabled            :
```

This command retrieves the configuration settings for the Service Manager Incident Management feature.

### Example 7: Get configuration settings for Service Manager
```
PS C:\>Get-SCSMSetting
DisplayName       : Data Retention Settings
ChangeRequestDays : 365
IncidentDays      : 90
ProblemDays       : 365
HistoryDays       : 365


DisplayName                        : Problem Settings
MaxAttachments                     : 10
MaxAttachmentSize                  : 64
PriorityMatrix                     : 
PriorityMaxValue                   : 
PriorityMinValue                   : 
ProblemIdPrefix                    : PR
Priority_UrgencyLowImpactHigh      : 
Priority_UrgencyLowImpactMedium    : 
Priority_UrgencyLowImpactLow       : 
Priority_UrgencyMediumImpactHigh   : 
Priority_UrgencyMediumImpactMedium : 
Priority_UrgencyMediumImpactLow    : 
Priority_UrgencyHighImpactHigh     : 
Priority_UrgencyHighImpactMedium   : 
Priority_UrgencyHighImpactLow      : 


DisplayName                                      : Activity Settings
SystemWorkItemActivityDependentActivityIdPrefix  : DA
SystemWorkItemActivityIdPrefix                   : AC
SystemWorkItemActivityManualActivityIdPrefix     : MA
SystemWorkItemActivityParallelActivityIdPrefix   : PA
SystemWorkItemActivityReviewActivityIdPrefix     : RA
SystemWorkItemActivitySequentialActivityIdPrefix : SA


DisplayName                    : Knowledge Management Settings
SystemKnowledgeArticleIdPrefix : KA


DisplayName                         : Change Request Settings
MaxFileAttachmentsCount             : 10
MaxFileAttachmentSizeinKB           : 64
SystemWorkItemChangeRequestIdPrefix : CR


DisplayName                         : Release Management Settings
MaxFileAttachmentsCount             : 10
MaxFileAttachmentSizeinKB           : 64
SystemWorkItemReleaseRecordIdPrefix : RR


DisplayName                        : Incident Settings
PrefixForId                        : IR
MaxAttachments                     : 10
MaxAttachmentSize                  : 2048
DefaultTierQueue                   : 
Priority_UrgencyLowImpactLow       : 
Priority_UrgencyLowImpactMedium    : 
Priority_UrgencyLowImpactHigh      : 
Priority_UrgencyMediumImpactLow    : 
Priority_UrgencyMediumImpactMedium : 
Priority_UrgencyMediumImpactHigh   : 
Priority_UrgencyHighImpactLow      : 
Priority_UrgencyHighImpactMedium   : 
Priority_UrgencyHighImpactHigh     : 
Priority1ResolutionTime            : 0
Priority2ResolutionTime            : 0
Priority3ResolutionTime            : 0
Priority4ResolutionTime            : 0
Priority5ResolutionTime            : 0
Priority6ResolutionTime            : 0
Priority7ResolutionTime            : 0
Priority8ResolutionTime            : 0
Priority9ResolutionTime            : 0
OpsMgrWebConsoleUrl                : 
SMTPDropFolder                     : 
SMTPBadFolder                      : 
MaximumEmailItems                  : 
EmailProcesingIsEnabled            :
```

This command retrieves all the configuration settings for Service Manager.

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

### -DisplayName
Specifies the value of the display name property of the setting to retrieve.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the setting to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
You can pipe one of the following solution settings to the *DisplayName* parameter:

- Activity Settings
- Release Management Settings
- Knowledge Management Settings
- Problem Settings
- Data Retention Settings
- Service Request Settings
- Incident Settings
- Change Request Settings

### System.Guid
You can pipe a GUID of a solution settings object to the *Id* parameter.
You can retrieve that GUID from the **__EnterpriseManagementObject** property of a solution settings object by using the following command:

`PS C:\\\> Get-SCSMSetting | ForEach-Object {$_.__EnterpriseManagementObject} | Format_Table -Property ID,DisplayName -AutoSize`

## OUTPUTS

### System.WorkItem.Incident.GeneralSetting
This cmdlet returns configuration settings of System Center Service Manager.

## NOTES

## RELATED LINKS

[Update-SCSMSetting](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMSetting.md)

