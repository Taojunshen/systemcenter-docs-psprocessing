---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCOpsMgrConnection.md
schema: 2.0.0
ms.assetid: 5AF5E124-ABBA-4CB9-8C58-5F970B56AC0B
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPROMonitor.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPROMonitor.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPROMonitor.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCPROMonitor

## SYNOPSIS
Gets a PRO monitor object from Operations Manager.

## SYNTAX

### PROTargetType (Default)
```
Get-SCPROMonitor [-VMMServer <ServerConnection>] [-PROTargetType <PROTargetType>] [<CommonParameters>]
```

### Name
```
Get-SCPROMonitor [-VMMServer <ServerConnection>] -Name <String> -ManagementPackName <String>
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCPROMonitor** cmdlet gets one or more Performance and Resource Optimization (PRO) monitors from Operations Manager.

## EXAMPLES

### Example 1: Get all of the PRO monitors from Operations Manager
```
PS C:\>Get-SCPROMonitor
```

This command gets all PRO monitors from Operations Manager and displays details about each monitor.

### Example 2: Get a specific PRO monitor by its name
```
PS C:\>$PROMonitor = Get-SCPROMonitor -Name "System Center Virtual Machine Manager Maximum Dynamic Memory Monitor" -ManagementPackName "System Center Virtual Machine Manager PRO V2 HyperV Host Performance"
PS C:\> $PROMonitor
```

The first command gets the PRO monitor object witht he specified name and management pack name, and stores the object in the $PROMonitor variable.

The second command displays information about the monitor object stored in $PROMonitor.

### Example 3: Get all PRO monitors for a specific target type
```
PS C:\>Get-SCPROMonitor -PROTargetType VMHost
```

This command gets all PRO monitors that have the target type of VMHost, and displays information about each monitor.

## PARAMETERS

### -ManagementPackName
Specifies the name of a management pack.
To get a specific PRO monitor, use this parameter with the monitor's name property.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROTargetType
Specifies the PRO target type.
The acceptable values for this parameter are:

- Cloud
- ComputerTier
- HostCluster
- ServiceInstance
- Unspecified
- VM
- VMHost
- VMMServer

```yaml
Type: PROTargetType
Parameter Sets: PROTargetType
Aliases: 
Accepted values: VM, Unspecified, VMHost, HostCluster, VMMServer, ServiceInstance, ComputerTier, Cloud

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### PROMonitor
This cmdlet returns a **PROMonitor** object.

## NOTES

## RELATED LINKS

[Get-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCOpsMgrConnection.md)

[Get-SCPROMonitorConfiguration](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPROMonitorConfiguration.md)

[Get-SCPROMonitorState](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCPROMonitorState.md)

