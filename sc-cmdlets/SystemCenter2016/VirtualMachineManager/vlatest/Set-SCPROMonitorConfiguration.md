---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E078436A-1719-4CA6-8DC1-725865E107EB
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROMonitorConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROMonitorConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROMonitorConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPROMonitorConfiguration

## SYNOPSIS
Updates the properties of a PRO monitor configuration.

## SYNTAX

### Inherit
```
Set-SCPROMonitorConfiguration [-VMMServer <ServerConnection>]
 -PROMonitorConfiguration <PROMonitorConfiguration> [-Inherit] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### EditSetting
```
Set-SCPROMonitorConfiguration [-VMMServer <ServerConnection>]
 -PROMonitorConfiguration <PROMonitorConfiguration> -AutomaticMode <Boolean> -MonitoringEnabled <Boolean>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPROMonitorConfiguration** cmdlet updates the properties of one or more Performance and Resource Optimization (PRO) monitor configuration objects.
Properties that can be set include whether monitoring and automatic remediation are enabled.

## EXAMPLES

### Example 1: Enable monitoring and automatic remediation for a specific PRO monitor
```
PS C:\> $PROMonitor = Get-SCPROMonitor -Name "System Center Virtual Machine Manager Maximum Dynamic Memory Monitor" -ManagementPackName "System Center Virtual Machine Manager PRO V2 HyperV Host Performance"
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> $PROMonitorConfig = Get-SCPROMonitorConfiguration -PROMonitor $PROMonitor -VMHost $VMHost
PS C:\> Set-SCPROMOnitorConfiguration -PROMonitorConfiguration $PROMonitorConfig -MonitoringEnabled $True -AutomaticMode $True
```

The first command gets the PRO monitor object with the specified name and management pack name and stores the object in the $PROMonitor variable.

The second command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The third command gets the PRO monitor configuration object for the PRO monitor stored in $PROMonitor on VMHost01 and stores the object in the $PROMonitorConfig variable.

The last command enables monitoring and automatic remediation for the PRO monitor configuration stored in $PROMonitorConfig.

### Example 2: Disable automatic remediation for all PRO monitors on a specified host
```
PS C:\> $VMHost = Get-SCVMHost -ComputerName "VMHost01.Contoso.com"
PS C:\> $PROMonitorConfigs = @(Get-SCPROMonitorConfiguration -VMHost $VMHost)
PS C:\> ForEach ($PROMonitorConfig in $PROMonitorConfigs) {Set-SCPROMonitorConfiguration -PROMonitorConfiguration $PROMonitorConfig -MonitoringEnabled $True -AutomaticMode $False}
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command gets all PRO monitor configuration objects on VMHost01 and stores the objects in the $PROMonitorConfigs object array.

The last command uses the **ForEach** statement to iterate through each PRO monitor configuration object stored in $PROMonitorConfigs and disables automatic remediation for each monitor configuration.

## PARAMETERS

### -AutomaticMode
Indicates whether dynamic optimization automatically migrates virtual machines in order to load balance.

```yaml
Type: Boolean
Parameter Sets: EditSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Inherit
Indicates that settings are inherited from the parent host group.

```yaml
Type: SwitchParameter
Parameter Sets: Inherit
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

### -MonitoringEnabled
Indicates whether monitoring is enabled for a PRO monitor.

```yaml
Type: Boolean
Parameter Sets: EditSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PROMonitorConfiguration
Specifies a PRO monitor configuration object.

```yaml
Type: PROMonitorConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### PROMonitorConfiguration
This cmdlet returns a **PROMonitorConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCPROMonitor](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitor.md)

[Get-SCPROMonitorConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROMonitorConfiguration.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHost.md)

