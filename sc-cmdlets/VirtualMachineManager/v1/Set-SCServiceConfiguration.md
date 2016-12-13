---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCCloud.md
schema: 2.0.0
ms.assetid: 27D03751-D3D4-4342-A709-336F8C904D63
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServiceConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServiceConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCServiceConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCServiceConfiguration

## SYNOPSIS
Modifies the properties of an undeployed service configuration object stored in the VMM library.

## SYNTAX

### HostGroup (Default)
```
Set-SCServiceConfiguration [-VMHostGroup <HostGroup>] [-VMMServer <ServerConnection>] [-Name <String>]
 [-Description <String>] [-ServicePriority <String>] [-Tag <String>] [-CostCenter <String>]
 -ServiceConfiguration <ServiceConfiguration> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Cloud
```
Set-SCServiceConfiguration -Cloud <Cloud> [-VMMServer <ServerConnection>] [-Name <String>]
 [-Description <String>] [-ServicePriority <String>] [-Tag <String>] [-CostCenter <String>]
 -ServiceConfiguration <ServiceConfiguration> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCServiceConfiguration** cmdlet modifies the properties of an undeployed service configuration object stored in the Virtual Machine Manager (VMM) library.

## EXAMPLES

### Example 1: Set the priority for a Service Configuration object in a cloud
```
PS C:\>$SvcConfig = Get-SCServiceConfiguration -Name "Service02"
PS C:\> $Cloud = Get-SCCloud -Name "Production"
PS C:\> Set-SCServiceConfiguration -ServiceConfiguration $SvcConfig -Cloud $Cloud -ServicePriority "Normal"
```

The first command gets the service configuration object named Service02 and stores the object in the $SvcConfig variable.

The second command gets the private cloud object named Production and stores the object in the $Cloud variable.

The last command sets the priority for the service configuration object tstored in $SvcConfig to Normal.

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
Specifies the name of a VMM object.

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

### -ServiceConfiguration
Specifies a service configuration object.

```yaml
Type: ServiceConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### ServiceConfiguration
This cmdlet returns a **ServiceConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCCloud](xref:VirtualMachineManager/v1/Get-SCCloud.md)

[Get-SCServiceConfiguration](xref:VirtualMachineManager/v1/Get-SCServiceConfiguration.md)

[New-SCServiceConfiguration](xref:VirtualMachineManager/v1/New-SCServiceConfiguration.md)

[Remove-SCServiceConfiguration](xref:VirtualMachineManager/v1/Remove-SCServiceConfiguration.md)

[Update-SCServiceConfiguration](xref:VirtualMachineManager/v1/Update-SCServiceConfiguration.md)

