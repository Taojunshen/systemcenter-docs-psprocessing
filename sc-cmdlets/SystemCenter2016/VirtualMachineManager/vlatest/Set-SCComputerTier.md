---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AEA04545-6859-4E82-84A4-E9283ADD3089
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTier.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTier.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCComputerTier.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCComputerTier

## SYNOPSIS
Modifies the properties of a VMM computer tier object.

## SYNTAX

```
Set-SCComputerTier -ComputerTier <ComputerTier> [-Name <String>] [-Description <String>]
 [-InstanceMaximumCount <Int32>] [-InstanceMinimumCount <Int32>] [-ServicingType <ServicingTypeValues>]
 [-AvailabilitySetName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCComputerTier** cmdlet modifies the properties of a Virtual Machine Manager (VMM) computer tier object.

## EXAMPLES

### Example 1: Set the maximum virtual machine count for a computer tier
```
PS C:\> $Service = Get-SCService -Name "Service01"
PS C:\> $Tier = Get-SCComputerTier -Service $Service
PS C:\> Set-SCComputerTier -ComputerTier $Tier -InstanceMaximumCount 10
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command gets the computer tier for the service stored in $Service and stores the object in the $Tier vairable.

The last command sets the maximum virtual machine count for the computer tier stored in $Tier to 10.

## PARAMETERS

### -AvailabilitySetName
Specifies the name of an availability set.

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

### -ComputerTier
Specifies a computer tier object.

```yaml
Type: ComputerTier
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Description
Specifies a description for the computer tier object.

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

### -InstanceMaximumCount
Specifies the maximum number of virtual machines to which a service instance can scale out.

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

### -InstanceMinimumCount
Specifies the minimum number of virtual machines to which a service instance can scale in.

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

### -ServicingType
Specifies the type of servicing for a service.
Valid values are: UseStandardServicing, UseImageBasedServicing.

```yaml
Type: ServicingTypeValues
Parameter Sets: (All)
Aliases: 
Accepted values: UseStandardServicing, UseImageBasedServicing

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

### ComputerTier
This cmdlet returns a **ComputerTier** object.

## NOTES

## RELATED LINKS

[Get-SCComputerTier](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCComputerTier.md)

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

