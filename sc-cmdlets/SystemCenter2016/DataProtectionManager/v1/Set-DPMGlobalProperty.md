---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMGlobalProperty.md
schema: 2.0.0
ms.assetid: CBA67457-C99E-4674-B81F-2001FBA7137A
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMGlobalProperty.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMGlobalProperty.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/v1/Set-DPMGlobalProperty.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMGlobalProperty

## SYNOPSIS
Sets the global properties for a DPM installation.

## SYNTAX

### IsNetworkChecksumRequired
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -IsNetworkChecksumRequired <Boolean> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### TruncateSharePointDbLogs
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -TruncateSharePointDbLogs <Boolean> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### LibraryRefreshInterval
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -LibraryRefreshInterval <Int32> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### AllowLocalDataProtection
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -AllowLocalDataProtection <Boolean> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ExchangeSCRProtection
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -ExchangeSCRProtection <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### RegisteredWriters
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -RegisteredWriters <Guid[]> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ConsiderForAutoDeployment
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -ConsiderForAutoDeployment <Boolean> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### MaxCapacityForClientAutoDeployment
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -MaxCapacityForClientAutoDeployment <Int32> [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### KnownVMMServers
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -KnownVMMServers <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### HyperVPagefileExclusions
```
Set-DPMGlobalProperty [[-DPMServerName] <String>] -HyperVPagefileExclusions <String> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMGlobalProperty** cmdlet sets the global properties for a System Center 2016 - Data Protection Manager (DPM) installation.

## EXAMPLES

### Example 1: Exclude page file VHDs
```
PS C:\>Set-DPMGlobalProperty -DPMServerName "Contoso-DPMServer" -HyperVPagefileExclusions "*_pagefile.vhd"
```

This command excludes all protected VHDs with names that include the string _pagefile.vhd on the server named Contoso-DPMServer.

### Example 2: Exclude VHDs using wildcard expressions exclusions
```
PS C:\>Set-DPMGlobalProperty -DPMServerName "Contoso-DPMServer" -HyperVPagefileExclusions "*_pagefile.vhd,*mypgf*.vhd*"
```

This command excludes VHD files that include the strings mypgf and pagefile.vhd in their names.

### Example 3: Remove all VHD exclusions
```
PS C:\>Set-DPMGlobalProperty -DPMServerName "Contoso-DPMServer" -HyperVPagefileExclusions ""
```

This command removes all existing exclusions by specifying an empty list for the *HyperVPagefileExclusions* parameter.

## PARAMETERS

### -AllowLocalDataProtection
Indicates whether a DPM server can protect data sources on the same computer on which it is installed.

```yaml
Type: Boolean
Parameter Sets: AllowLocalDataProtection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsiderForAutoDeployment
Indicates whether to consider a DPM server for client protection.

```yaml
Type: Boolean
Parameter Sets: ConsiderForAutoDeployment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet acts.

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

### -ExchangeSCRProtection
Specifies the name of a Microsoft Exchange Server Standby Continuous Replication (SCR) Server.
To specify the names of multiple servers, list them individually, separated by commas.

```yaml
Type: String
Parameter Sets: ExchangeSCRProtection
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HyperVPagefileExclusions
Specifies the name of a virtual hard disk drive (VHD) pagefile to exclude from backup jobs for a firstref_virtualname data source.
To specify the names of multiple VHD pagefiles, list them individually, separated by commas.
This parameter also accepts wildcard values.

```yaml
Type: String
Parameter Sets: HyperVPagefileExclusions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsNetworkChecksumRequired
Indicates whether to apply a checksum to verify data transferred over a network.

```yaml
Type: Boolean
Parameter Sets: IsNetworkChecksumRequired
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KnownVMMServers
Specifies a vmm12sp1_long server that communicates with DPM to provide support for virtual machine mobility scenarios.
If you specify this parameter, DPM stores the vmm12short server information and configures its services to communicate with the vmm12short.

```yaml
Type: String
Parameter Sets: KnownVMMServers
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LibraryRefreshInterval
Specifies the refresh interval for gathering information about shared libraries.

```yaml
Type: Int32
Parameter Sets: LibraryRefreshInterval
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxCapacityForClientAutoDeployment
Specifies the maximum number of client computers that a DPM server can protect.
Set this value to guarantee that DPM protects a reasonable number of client computers if auto-deployment is enabled by specifying the *ConsiderForAutoDeployment* parameter.

```yaml
Type: Int32
Parameter Sets: MaxCapacityForClientAutoDeployment
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RegisteredWriters
For internal use only.

```yaml
Type: Guid[]
Parameter Sets: RegisteredWriters
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TruncateSharePointDbLogs
Indicates whether to truncate SharePoint database logs during replication.

```yaml
Type: Boolean
Parameter Sets: TruncateSharePointDbLogs
Aliases: 

Required: True
Position: Named
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-DPMGlobalProperty](xref:SystemCenter2016/DataProtectionManager/v1/Get-DPMGlobalProperty.md)

