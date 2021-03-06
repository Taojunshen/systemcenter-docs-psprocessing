---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6D8900B1-D2EC-4D6F-8D7D-82F65610BD92
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCFabricRole

## SYNOPSIS
Modifies a fabric role.

## SYNTAX

```
Set-SCFabricRole [-VMMServer <ServerConnection>] [-FabricRole] <FabricRole>
 [-LoadBalancerConfiguration <LoadBalancerRoleConfiguration>]
 [-GatewayConfiguration <GatewayRoleConfiguration>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCFabricRole** cmdlet modifies a fabric role in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Modify values for a fabric role
```
PS C:\> $FabricRoleConfiguration = New-SCLoadBalancerRoleConfiguration -LBManagerIPAddress "15.16.17.249"" -NatIPExemptions $NatIPExemptions -VipPools $VipPools
PS C:\> $FabricRole = Set-SCFabricRole -FabricRole $FabricRole -LoadBalancerConfiguration $FabricRoleConfiguration
```

The first command creates a configuration by using the **New-SCLoadBalancerRoleConfiguration** cmdlet, and then stores it in the $FabricRoleConfiguration variable.
The command includes values in variables created by other commands.

The second command updates the existing load balancer fabric role with the configuration in $FabricRoleConfiguration.

## PARAMETERS

### -FabricRole
Specifies a **FabricRole** object.

```yaml
Type: FabricRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -GatewayConfiguration
Specifies a **GatewayRoleConfiguration** object.

```yaml
Type: GatewayRoleConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -LoadBalancerConfiguration
Specifies a **LoadBalancerRoleConfiguration** object.

```yaml
Type: LoadBalancerRoleConfiguration
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

## NOTES

## RELATED LINKS

[Get-SCFabricRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md)

[New-SCLoadBalancerRoleConfiguration](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCLoadBalancerRoleConfiguration.md)

