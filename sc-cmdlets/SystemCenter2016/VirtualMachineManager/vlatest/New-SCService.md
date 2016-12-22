---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CBC2B99C-C1B7-4DF9-A083-B9C0A50136E1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCService

## SYNOPSIS
Deploys a new service instance in VMM.

## SYNTAX

```
New-SCService [-PersistServiceConfiguration] [-Owner <String>] [-VMMServer <ServerConnection>]
 -ServiceConfiguration <ServiceConfiguration> [-UserRole <UserRole>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCService** cmdlet deploys a new service instance into the Virtual Machine Manager (VMM) environment.
You can create a service directly from a service template if no service instance configuration is needed, or from a service configuration.

## EXAMPLES

### Example 1: Deploy a service template using a service configuration that is stored in the library
```
PS C:\> $SvcConfig = Get-SCServiceConfiguration -Name "Service01"
PS C:\> Update-SCServiceConfiguration -ServiceConfiguration $SvcConfig
PS C:\> $NewService = New-SCService -ServiceConfiguration $SvcConfig 
PS C:\> $NewService
```

The first command gets the service configuration object named Contoso Service Configuration 01 and stores the object in the $SvcConfig variable.

The second command runs placement to update the service configuration stored in $SvcConfig.

The third command deploys the new service using the service configuration stored in $SvcConfig.

The last command displays the properties of the newly deployed service to the user.

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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

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

### -PersistServiceConfiguration
Indicates that the service deployment configuration is stored in the VMM library after the service is deployed.

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

### -UserRole
Specifies a user role object.

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

### Service
This cmdlet returns a **Service** object.

## NOTES

## RELATED LINKS

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

[Read-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCService.md)

[Remove-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCService.md)

[Resume-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md)

[Set-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md)

[Start-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCService.md)

[Stop-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCService.md)

[Suspend-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCService.md)

[Update-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCService.md)

