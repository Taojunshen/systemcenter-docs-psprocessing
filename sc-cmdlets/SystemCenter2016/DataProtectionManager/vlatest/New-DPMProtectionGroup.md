---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3656318D-30D9-4415-8DC8-0F88550BA8AE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/New-DPMProtectionGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-DPMProtectionGroup

## SYNOPSIS
Creates a protection group on the DPM server.

## SYNTAX

```
New-DPMProtectionGroup [[-DPMServerName] <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-DPMProtectionGroup** cmdlet creates a protection group on a System Center 2016 - Data Protection Manager (DPM) server.
This is the first step to create a protection group.
This cmdlet returns a new protection group object on which you can perform the remaining steps of creating a protection group.
However, the protection group is not created until you run the Set-DPMProtectionGroup cmdlet.

Use the following cmdlets to create a new protection group.
Use one or more cmdlets from each step:

1.
**New-DPMProtectionGroup**

2.
**Add-DPMChildDatasource**, **Remove-DPMChildDatasource**, **Set-DPMDatasourceProtectionOption**, **Set-DPMProtectionJobStartTime**

3.
**Set-DPMProtectionType**

4.
**Set-DPMReplicaCreationMethod**

5.
**Set-DPMPolicyObjective**, **Set-DPMPolicySchedule** (Short term)

6.
**Get-DPMDatasourceDiskAllocation**

7.
**Set-DPMDatasourceDiskAllocation**

8.
**Set-DPMPolicyObjective**, **Set-DPMPolicySchedule** (Long term)

9.
**Set-DPMTapeBackupOption**

10.
**Set-DPMProtectionGroup**

Depending on your choice in a previous step, some steps might not be applicable.
For example, if you set disk-based protection in step 3, steps 8 and 9 are not required.

It is important to remember that the protection group is created only after you run the **Set-DPMProtectionGroup** cmdlet.
Until you run **Set-DPMProtectionGroup**, the protection group exists only in memory.

## EXAMPLES

### Example 1: Create a protection group
```
PS C:\>New-DPMProtectionGroup -DPMServerName "DPMServer02" -Name "ProtectGroup01"
```

This command creates an instance of a protection group named ProtectGroup01 in the memory of the DPM server named DPMServer02.
This is the first step of creating the protection group.

## PARAMETERS

### -DPMServerName
Specifies the name of a DPM server on which this cmdlet creates a protection group.
If you do not specify a name, the cmdlet uses the current computer name.

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

### -Name
Specifies a name for the protection group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ProtectionGroup

## NOTES

## RELATED LINKS

[Update-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Update-DPMProtectionGroup.md)

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Rename-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Rename-DPMProtectionGroup.md)

[Set-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionGroup.md)

