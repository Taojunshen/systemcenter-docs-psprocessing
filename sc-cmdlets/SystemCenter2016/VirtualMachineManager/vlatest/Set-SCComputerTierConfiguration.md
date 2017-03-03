---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BD906D67-7022-43DD-B430-321A2E7B4C82
updated_at: 12/22/2016 5:13 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierConfiguration.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierConfiguration.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17600c3a31aaf782880f045fab1671fdd067cc23/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTierConfiguration.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCComputerTierConfiguration

## SYNOPSIS
Configures the computer tier configuration object in an undeployed service configuration.

## SYNTAX

```
Set-SCComputerTierConfiguration -ComputerTierConfiguration <BaseComputerTierConfiguration> [-TimeZone <Int32>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCComputerTierConfiguration** cmdlet configures the computer tier configuration object in an undeployed service configuration.

## EXAMPLES

### Example 1: Configure the computer tier within a service configuration
```
PS C:\> $ServiceConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> $TierConfig = Get-SCComputerTierConfiguration -ServiceConfiguration $ServiceConfig
PS C:\> $UpdatedConfig = Set-SCComputerTierConfiguration -ComputerTierConfiguration $TierConfig -TimeZone 085
PS C:\> $UpdatedConfig
```

The first command gets the service configuration object named Service01 and stores the object in the $ServiceConfig variable.

The second command gets the computer tier configuration for the service configuration stored in $ServiceConfig and stores the object in the $TierConfig variable.

The third command sets the timezone property for the computer tier configuration stored in $TierConfig and stores the computer tier configuration in the $UpdatedConfig variable.

The last command displays information about the updated computer tier configuration stored in $UpdatedConfig to the user.

## PARAMETERS

### -ComputerTierConfiguration
Specifies a computer tier configuration object.

```yaml
Type: BaseComputerTierConfiguration
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
To obtain a user role, use the **Get-SCUserRole** cmdlet.
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

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see [Microsoft Time Zone Index Values](http://go.microsoft.com/fwlink/?LinkId=120935) at `http://go.microsoft.com/fwlink/?LinkId=120935`.
If no time zone is specified, the default time zone used for a virtual machine is the same time zone setting that is on the virtual machine host. 


Example format to specify the GMT Standard Time zone: `-TimeZone 085`

```yaml
Type: Int32
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

### ComputerTierConfiguration
This cmdlet returns a **ComputerTierConfiguration** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTierConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTierConfiguration.md)

