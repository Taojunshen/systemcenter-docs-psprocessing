---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceConfiguration.md
schema: 2.0.0
ms.assetid: A8FE9073-ABE6-4E75-BAD8-BC12A5E5C705
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServiceConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServiceConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCServiceConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCServiceConfiguration

## SYNOPSIS
Creates a service configuration from a service template.

## SYNTAX

### HostGroup
```
New-SCServiceConfiguration [-Name] <String> [-Description <String>] [-VMMServer <ServerConnection>]
 -ServiceTemplate <ServiceTemplate> [-ServicePriority <String>] -VMHostGroup <HostGroup> [-Tag <String>]
 [-CostCenter <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Cloud
```
New-SCServiceConfiguration [-Name] <String> [-Description <String>] [-VMMServer <ServerConnection>]
 -ServiceTemplate <ServiceTemplate> [-ServicePriority <String>] -Cloud <Cloud> [-Tag <String>]
 [-CostCenter <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCServiceConfiguration** cmdlet creates a service configuration from a service template.
The service configuration contains instance-specific values that are used when the service is deployed.

## EXAMPLES

### Example 1: Create a service configuration for a host group
```
PS C:\>$HostGroup = Get-SCVMHostGroup | where { $_.Path -eq "All Hosts\HostGroup02\Production" }
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $ServiceConfig = New-SCServiceConfiguration -ServiceTemplate $ServiceTemplate -Name "Service01" -VMHostGroup $HostGroup  -Description "Contoso Service 01" -ServicePriority High -CostCenter 1033 
PS C:\> $ServiceConfig
```

The first command gets the host group object with the path All Hosts\HostGroup02\Production and stores the object in the $HostGroup variable.

The second command gets the service template object named ServiceTemplate01 and stores it in the $ServiceTemplate variable.

The third command creates a service configuration object in the library for the host group stored in $HostGroup using the service template object stored in $ServiceTemplate.
The command then stores the new service configuration object in the $ServiceConfig variable.

The last command displays the properties of the new service configuration object to the user.

### Example 2: Create a service configuration for a private cloud
```
PS C:\>$Cloud = Get-SCCloud -Name "Production"
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $ServiceConfig = New-SCServiceConfiguration -ServiceTemplate $ServiceTemplate -Name "Service02" -Cloud $Cloud  -Description "Contoso Cloud Service" -ServicePriority High -CostCenter 1033 
PS C:\> $ServiceConfig
```

The first command gets the private cloud object named Production and stores the object in the $Cloud variable.

The second command gets the service template object named ServiceTemplate01 and stores it in the $ServiceTemplate variable.

The third command creates a service configuration object in the library for the private cloud stored in $Cloud using the service template object stored in $ServiceTemplate.
The command then stores the new service configuration object in the $ServiceConfig variable.

The last command displays the properties of the new service configuration object to the user.

## PARAMETERS

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: Cloud
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CostCenter
Specifies the cost center for a virtual machine so that you can collect data about the allocation of virtual machines (or resources allocated to virtual machines) to make use of in your billing system.

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

### -Description
Specifies a description for the service configuration.

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

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the Get-SCUserRole cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -ServicePriority
Specifies the priority for a service.
Valid values are: Normal, Low, High.
Default value: Normal.

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

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

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

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: HostGroup
Aliases: 

Required: True
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

### ServiceConfiguration
This cmdlet returns a **ServiceConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceConfiguration.md)

[Remove-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServiceConfiguration.md)

[Set-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCServiceConfiguration.md)

[Update-SCServiceConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCServiceConfiguration.md)

