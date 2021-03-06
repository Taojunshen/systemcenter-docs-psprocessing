---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6D71476B-C88C-4C65-B004-0423102F1C9D
updated_at: 2/28/2017 10:37 AM
ms.date: 2/28/2017
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCloudSubscriptionSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCloudSubscriptionSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/c25d8a48f4a3ec91a928988bdcfc4a813011aa4c/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCloudSubscriptionSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMCloudSubscriptionSetting

## SYNOPSIS
Updates subscription settings in Azure Online Backup for a DPM server.

## SYNTAX

### Commit

```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-SecurityPin] <SecurityPinValue> [-Commit] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StagingArea
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-StagingAreaPath] <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Encryption
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-EncryptionPassphrase] <SecureString> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NoProxy
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-NoProxy] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ProxyServer
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-ProxyServer] <String> [-ProxyPort] <Int32> [[-ProxyUsername] <String>] [[-ProxyPassword] <SecureString>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NoThrottle
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-NoThrottle] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Throttle
```
Set-DPMCloudSubscriptionSetting [[-DPMServerName] <String>] [-SubscriptionSetting] <CloudSubscriptionSetting>
 [-WorkDay] <DayOfWeek[]> [-StartWorkHour] <TimeSpan> [-EndWorkHour] <TimeSpan> [-WorkHourBandwidth] <UInt32>
 [-NonWorkHourBandwidth] <UInt32> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMCloudSubscriptionSetting** cmdlet updates subscription settings in Windows Azure Online Backup for a System Center 2016 - Data Protection Manager (DPM) server.

## EXAMPLES

### Example 1: Specify Azure Online Backup options for a DPM server
```
PS C:\>$Setting = Get-DPMCloudSubscriptionSetting -DPMServerName "TestingServer"
PS C:\> Set-DPMCloudSubscriptionSetting -DPMServerName "TestingServer" -SubscriptionSetting $Setting -StagingAreaPath "C:\StagingArea"
PS C:\> Set-DPMCloudSubscriptionSetting -DPMServerName "TestingServer" -SubscriptionSetting $Setting -NoProxy
PS C:\> $Passphrase = ConvertTo-SecureString -string "passphrase123456789" -AsPlainText -Force
PS C:\> Set-DPMCloudSubscriptionSetting -DPMServerName "TestingServer" -SubscriptionSetting $Setting -EncryptionPassphrase $Passphrase
PS C:\> Set-DPMCloudSubscriptionSetting -DPMServerName "TestingServer" -SubscriptionSetting $Setting -Commit
```

The first command gets the subscription settings for the server named TestingServer, and then stores the settings in the $Setting variable.

The second command specifies C:\StagingArea as the staging area for backup files from TestingServer.

The third command indicates that the backup does not use a proxy server.

The fourth command converts the string passphrase123456789 to a secure string, and then stores the secure string in the $Passphrase variable.

The fifth command sets the secure string in $Passphrase as the password for encrypting backups from TestingServer.

The final command saves the backup options that you set in previous commands.

## PARAMETERS

### -Commit
Indicates that DPM saves the Azure Online Backup settings.

```yaml
Type: SwitchParameter
Parameter Sets: Commit
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of the DPM server for which this cmdlet updates settings.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionPassphrase
Specifies a secure string that contains a passphrase used to encrypt backups from the DPM server.

```yaml
Type: SecureString
Parameter Sets: Encryption
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EndWorkHour
Specifies the end of the time range when DPM uses throttling as specified in the *WorkHourBandwidth* parameter.
Use this parameter together with the *StartWorkHour* parameter.

```yaml
Type: TimeSpan
Parameter Sets: Throttle
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NonWorkHourBandwidth
Specifies throttling settings for hours outside the range that the *StartWorkHour* and *EndWorkHour* parameters define.

```yaml
Type: UInt32
Parameter Sets: Throttle
Aliases: 

Required: True
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NoProxy
Indicates that the cmdlet does not use a proxy server.

```yaml
Type: SwitchParameter
Parameter Sets: NoProxy
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoThrottle
Indicates that the cmdlet does not use bandwidth throttling.

```yaml
Type: SwitchParameter
Parameter Sets: NoThrottle
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyPassword
Specifies a secure string that contains the password for the proxy server.

```yaml
Type: SecureString
Parameter Sets: ProxyServer
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyPort
Specifies a port number for the proxy server.

```yaml
Type: Int32
Parameter Sets: ProxyServer
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProxyServer
Specifies the name of the proxy server.

```yaml
Type: String
Parameter Sets: ProxyServer
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProxyUsername
Specifies the user name that you use to log on to the proxy server.

```yaml
Type: String
Parameter Sets: ProxyServer
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityPin
Specifies the Security PIN value for the recovery services vault to which this DPM server is added. This is mandatory if [Security Features are enabled](https://docs.microsoft.com/azure/backup/backup-azure-security-feature#enabling-security-features) for the related Recovery Services vault and encryption passphrase is being changed. To access Security PIN, go to Azure portal and navigate to your Recovery Services vault > Settings > Properties > Generate Security PIN.

```yaml
Type: String
Parameter Sets: Commit
Aliases: 

Required: False
Position: 
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StagingAreaPath
Specifies the path to which you download backups before you recover them to their final location.
Ensure that the location you specify has sufficient space to hold the backups.

```yaml
Type: String
Parameter Sets: StagingArea
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StartWorkHour
Specifies the start of the time range when the throttling settings in the *WorkHourBandwidth* parameter are in effect.
Use this parameter together with the *EndWorkHour* parameter.

```yaml
Type: TimeSpan
Parameter Sets: Throttle
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```


### -SubscriptionSetting
Specifies a **Subscription** object that contains the subscription settings.
To obtain a **Subscription** object, use the Get-DPMCloudSubscription cmdlet.

```yaml
Type: CloudSubscriptionSetting
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkDay
Specifies the days of the week when Azure Online Backup runs.

The acceptable values for this parameter are:

- Sunday
- Monday
- Tuesday
- Wednesday
- Thursday
- Friday
- Saturday

```yaml
Type: DayOfWeek[]
Parameter Sets: Throttle
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkHourBandwidth
Specifies the bandwidth that Azure Online Backup uses during working hours.

```yaml
Type: UInt32
Parameter Sets: Throttle
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMCloudSubscription](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscription.md)

[Get-DPMCloudSubscriptionSetting](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMCloudSubscriptionSetting.md)

