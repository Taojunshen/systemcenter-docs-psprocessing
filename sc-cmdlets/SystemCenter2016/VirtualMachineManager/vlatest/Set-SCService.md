---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCService.md
schema: 2.0.0
ms.assetid: 94395B73-D98E-4B77-8C1D-4F180E0D5605
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCService

## SYNOPSIS
Modifies a VMM service instance.

## SYNTAX

### UnspecifiedSet (Default)
```
Set-SCService [-Name <String>] [-Description <String>] [-Owner <String>] [-CostCenter <String>]
 [-ServicePriority <ServicePriority>] [-VMMServer <ServerConnection>] [-Service] <Service>
 [-UserRole <UserRole>] [-Cloud <Cloud>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### PendingST
```
Set-SCService [-Name <String>] [-Description <String>] [-Owner <String>] [-CostCenter <String>]
 [-ServicePriority <ServicePriority>] [-VMMServer <ServerConnection>] [-Service] <Service>
 -PendingServiceTemplate <ServiceTemplate> [-UserRole <UserRole>] [-Cloud <Cloud>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### DismissST
```
Set-SCService [-Name <String>] [-Description <String>] [-Owner <String>] [-CostCenter <String>]
 [-ServicePriority <ServicePriority>] [-VMMServer <ServerConnection>] [-Service] <Service>
 [-DismissPendingServiceTemplate] [-WhatIf] [-UserRole <UserRole>] [-Cloud <Cloud>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### CommitST
```
Set-SCService [-Name <String>] [-Description <String>] [-Owner <String>] [-CostCenter <String>]
 [-ServicePriority <ServicePriority>] [-VMMServer <ServerConnection>] [-Service] <Service>
 [-CommitPendingServiceTemplate] [-WhatIf] [-UserRole <UserRole>] [-Cloud <Cloud>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCService** cmdlet modifies a Virtual Machine Manager (VMM) service instance.

## EXAMPLES

### Example 1: Change the description and priority of a service
```
PS C:\>$Service = Get-SCService -Name "Service01"
PS C:\> Set-SCService -Service $Service -Description "Contoso Custom Service" -ServicePriority Normal
```

The first command command gets the service object named Service01 and stores the object in the $Service variable.

The second command updates the description and priority for the service stored in $Service.

### Example 2: Dismiss a pending service template
```
PS C:\>$Service = Get-SCService -Name "Service01"
PS C:\> Set-SCService -Service $Service -DismissPendingServiceTemplate
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command dismisses the pending servicing operation.

## PARAMETERS

### -Cloud
Specifies a private cloud object.

```yaml
Type: Cloud
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CommitPendingServiceTemplate
Applies the pending service template to the service instance.

```yaml
Type: SwitchParameter
Parameter Sets: CommitST
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
Specifies a description for the service instance.

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

### -DismissPendingServiceTemplate
Removes a pending service template from a service instance.

```yaml
Type: SwitchParameter
Parameter Sets: DismissST
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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

Example format: `-Owner "Contoso\PattiFuller"`
Example format: `-Owner "PattiFuller@Contoso"`

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

### -PendingServiceTemplate
Specifies a service template object that has been updated but not applied to the service instance.

```yaml
Type: ServiceTemplate
Parameter Sets: PendingST
Aliases: 

Required: True
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

### -Service
Specifies a VMM service object.

```yaml
Type: Service
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ServicePriority
Specifies the priority for a service.
Valid values are: Normal, Low, High.
Default value: Normal.

```yaml
Type: ServicePriority
Parameter Sets: (All)
Aliases: 
Accepted values: Normal, Low, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: DismissST, CommitST
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

### Service
This cmdlet returns a **Service** object.

## NOTES

## RELATED LINKS

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

[New-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md)

[Read-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCService.md)

[Remove-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCService.md)

[Resume-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md)

[Start-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCService.md)

[Stop-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCService.md)

[Suspend-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCService.md)

[Update-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCService.md)

