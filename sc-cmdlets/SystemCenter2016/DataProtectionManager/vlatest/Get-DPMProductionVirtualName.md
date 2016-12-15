---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProductionCluster.md
schema: 2.0.0
ms.assetid: F2E5A70B-3613-4563-AFBA-5F5AEE2E0C2B
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionVirtualName.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionVirtualName.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionVirtualName.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-DPMProductionVirtualName

## SYNOPSIS
Gets the virtual names for a cluster.

## SYNTAX

```
Get-DPMProductionVirtualName [-ProductionCluster] <Cluster> [-Async] [-Tag <Object>]
 [-Handler <System.EventHandler`1[Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.Inquiry.VNInquiryeventArgs]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-DPMProductionVirtualName** cmdlet gets the virtual names for a cluster on which a System Center 2016 - Data Protection Manager (DPM) protection agent is installed.

## EXAMPLES

### Example 1: Get the virtual names for a cluster
```
PS C:\>$PCluster = Get-DPMProductionCluster -DPMServerName "DPMServer02"
PS C:\> Get-DPMProductionVirtualName -ProductionCluster $PCluster
```

The first command gets the clusters that the DPM named DPMServer02 manages.
The command stores the result in the $PCluster variable.

The second command gets the virtual name of the clusters in $PCluster.

## PARAMETERS

### -Async
Indicates that the command runs asynchronously.
When you run a command asynchronously, the command prompt returns immediately even if the job takes an extended time to finish.

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

### -Handler
Specifies the event handler that the DPM calls when it receives an event.

```yaml
Type: System.EventHandler`1[Microsoft.Internal.EnterpriseStorage.Dls.UI.ObjectModel.Inquiry.VNInquiryeventArgs]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductionCluster
Specifies the name of a cluster of computers on which a DPM protection agent is installed.

```yaml
Type: Cluster
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Specifies a custom property that distinguishes the replies to each asynchronous call.
You can use parameter if you build a graphical user interface by using cmdlets.
Do not use this parameter if you work with the DPM Management Shell.

```yaml
Type: Object
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

## OUTPUTS

### VirtualName

## NOTES

## RELATED LINKS

[Get-DPMProductionCluster](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionCluster.md)

[Get-DPMProductionServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProductionServer.md)

