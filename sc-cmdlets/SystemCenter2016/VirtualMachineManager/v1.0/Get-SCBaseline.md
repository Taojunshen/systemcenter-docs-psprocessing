---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./New-SCBaseline.md
schema: 2.0.0
ms.assetid: 1E6F63BC-142D-4A66-BE1E-4548EB52D53C
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCBaseline.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCBaseline.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCBaseline.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCBaseline

## SYNOPSIS
Gets one or more baselines objects.

## SYNTAX

### ID (Default)
```
Get-SCBaseline [-VMMServer <ServerConnection>] [-ID <Guid>] [<CommonParameters>]
```

### Name
```
Get-SCBaseline [-VMMServer <ServerConnection>] [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCBaseline** cmdlet gets one or more baseline objects.
A baseline is a list of updates which, together with scope assignments, can grade the compliance of required updates for Virtual Machine Manager (VMM) fabric servers.

## EXAMPLES

### Example 1: Get a baseline by its name
```
PS C:\>Get-SCBaseline -Name "Security Baseline"
```

This command gets the baseline object named Security Baseline.

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Baseline
This cmdlet returns a **Baseline** object.

## NOTES

## RELATED LINKS

[New-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/v1.0/New-SCBaseline.md)

[Remove-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCBaseline.md)

[Set-SCBaseline](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCBaseline.md)

