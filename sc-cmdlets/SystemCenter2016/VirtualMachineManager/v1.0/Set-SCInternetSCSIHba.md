---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: eadbf80a-31d1-4fbb-9559-0f7f0765e48b
schema: 2.0.0
ms.assetid: 4A012B3A-B20C-4989-B414-F51BEF1C0372
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCInternetSCSIHba.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCInternetSCSIHba.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCInternetSCSIHba.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCInternetSCSIHba

## SYNOPSIS
Configures iSCSI initiator sessions and logs the initiator on to the iSCSI storage array.

## SYNTAX

### CreateSessionArray
```
Set-SCInternetSCSIHba -InternetSCSIHba <HostInternetSCSIHba> [-CreateSession] -StorageArray <StorageArray>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### CreateSession
```
Set-SCInternetSCSIHba -InternetSCSIHba <HostInternetSCSIHba> [-CreateSession]
 -TargetPortal <StorageiSCSIPortal> [-InitiatorIP <String>] [-TargetName <StorageEndpoint>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCInternetSCSIHba** cmdlet configures the iSCSI initiator on a virtual machine host.
**Set-InternetSCSIHba** also creates persistent connections to the iSCSI storage array either by explicitly specifying the initiator IP, target name, and target portal, or by allowing Virtual Machine Manager (VMM) to automatically create multiple connections to the iSCSI storage array based on subnet matching.

## EXAMPLES

### 1:
```

```

## PARAMETERS

### -CreateSession
Indicates that an iSCSI session is created.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorIP
Specifies an IP address for the iSCSI initiator.

```yaml
Type: String
Parameter Sets: CreateSession
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternetSCSIHba
Specifies an instance of an iSCSI initiator on a host.

```yaml
Type: HostInternetSCSIHba
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -StorageArray
Specifies a storage array object.
This can be a Fibre Channel or iSCSI storage sub-system that is used to store virtual machine configuration and virtual disks.

```yaml
Type: StorageArray
Parameter Sets: CreateSessionArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName
Specifies the name for an iSCSI storage array target.

```yaml
Type: StorageEndpoint
Parameter Sets: CreateSession
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetPortal
Specifies an iSCSI storage array target portal object.

```yaml
Type: StorageiSCSIPortal
Parameter Sets: CreateSession
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

### HostInternetSCSIHBA
This cmdlet returns a **HostInternetSCSIHBA** object.

## NOTES

## RELATED LINKS

