---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 29D63D92-47FB-4A87-A96E-4862983932DA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCVMConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCVMConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Update-SCVMConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCVMConfiguration

## SYNOPSIS
Updates the properties of a VMM virtual machine configuration object.

## SYNTAX

### FromVMConfig (Default)
```
Update-SCVMConfiguration [-VMConfiguration] <BaseVMConfiguration> [-ValidateOnly <Boolean>] [-VMName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### FromVMConfigList
```
Update-SCVMConfiguration
 -VMConfigurationList <System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.BaseVMConfiguration]>
 [-ValidateOnly <Boolean>] [-VMName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCVMConfiguration** cmdlet updates the properties of a Virtual Machine Manager (VMM) virtual machine configuration object.

## EXAMPLES

### Example 1: Update an existing virtual machine configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $VMConfig = Get-SCVMConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> Update-SCVMConfiguration -VMConfiguration $VMConfig[0] -ValidateOnly $True
```

The first command gets the service configuration object named Service01 from the VMM library and stores the object in the $ServiceConfig variable.

The second command gets the virtual machine configuration object for the service configuration stored in $ServiceConfig and stores the virtual machine configuration object in $VMConfig.

The last command sets the ValidateOnly property to True for the first configuration object stored in $VMConfig.

## PARAMETERS

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

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the **Get-SCUserRole** cmdlet.

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

### -VMConfiguration
Specifies a virtual machine configuration object.

```yaml
Type: BaseVMConfiguration
Parameter Sets: FromVMConfig
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMConfigurationList
Specifies a list of configuration objects.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.SystemCenter.VirtualMachineManager.BaseVMConfiguration]
Parameter Sets: FromVMConfigList
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMName
Specifies the name of a virtual machine to be placed on a physical host server.
Use this parameter to verify that another virtual machine with the same name is not already deployed on that host.

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

### -ValidateOnly
Indicates whether validation of the placement is performed, but placement is not actually performed.

```yaml
Type: Boolean
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

### ComputerConfig
This cmdlet returns a **ComputerConfig** object.

## NOTES
* Requires a VMM virtual machine configuration object, which can be obtained by using the **Get-SCVMConfiguration** cmdlet.

## RELATED LINKS

[Get-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMConfiguration.md)

[New-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMConfiguration.md)

[Remove-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMConfiguration.md)

[Set-SCVMConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMConfiguration.md)

