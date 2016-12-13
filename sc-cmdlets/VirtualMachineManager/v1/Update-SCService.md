---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCService.md
schema: 2.0.0
ms.assetid: BDE49CAB-B129-45AF-BF17-70153DAEED94
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Update-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Update-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Update-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Update-SCService

## SYNOPSIS
Updates a VMM service instance.

## SYNTAX

### Service (Default)
```
Update-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-ShowActions] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### WhatIf
```
Update-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-WhatIf] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Update-SCService** cmdlet updates an instance of a Virtual Machine Manager (VMM) service.
There are two servicing types you can use: conventional servicing and image-based servicing.

Conventional servicing applies updates to deployed virtual machines in place, without redeploying the service.
While fast, it does not allow changing a virtual hard disk, removing network adapters, or changing operating system settings (except for Windows Server roles and features).

Image-based servicing deploys new virtual machines to the service with the updates.
This type of servicing is used most often after updating the VHD for a tier, such as applying software updates to the program disk.

## EXAMPLES

### Example 1: Update a service by using conventional servicing
```
PS C:\>$Service = Get-SCService -Name "Service01"
PS C:\> $SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $PendingTemplate = New-SCServiceTemplate -ServiceTemplate $SvcTemplate -Name "ServiceTemplate01" -Release "RTM"
PS C:\> Set-SCService -Service $Service -PendingServiceTemplate $PendingTemplate
PS C:\> Update-SCService -Service $Service
```

The first command gets the service object named Service01, which is a deployed service, and stores the object in the $Service variable.

The second command gets the service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The third command creates an RTM release of the service template stored in $SvcTemplate.

The fifth command sets the pending template on the service instance to the updated service template stored in $PendingTemplate.

The last command updates Service01.

### Example 2: Update a service by using image-based servicing
```
PS C:\> $Service = Get-SCService -Name "Service02"
PS C:\> $SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate02"
PS C:\> $PendingTemplate = New-SCServiceTemplate -ServiceTemplate $SvcTemplate -Name "ServiceTemplate02" -Release "RTM"
PS C:\> $WebTier = Get-SCComputerTierTemplate -ServiceTemplate $PendingTemplate -Name "Web Tier"
PS C:\> $WebTemplate = Get-SCVMTemplate -ComputerTierTemplate $WebTier | Set-SCVMTemplate -MemoryMB 2048
PS C:\> $BaseDisk2 = Get-SCVirtualHardDisk -Name "Win2k8R2BaseDisk_Patched.vhd"
PS C:\> $VHD = Get-SCVirtualDiskDrive -VMTemplate $WebTemplate 
PS C:\> Remove-SCVirtualDiskDrive -VirtualDiskDrive $VHD
PS C:\> New-SCVirtualDiskDrive -VirtualHardDisk $BaseDisk2 -VMTemplate $WebTemplate -BootVolume -SystemVolume -Bus 0 -LUN 0 -IDE -VolumeType BootAndSystem

PS C:\> Set-SCService -Service $Service -PendingServiceTemplate $PendingTemplate 
PS C:\> Update-SCService -Service $Service
```

The first command gets the service object named Service02 and stores the object in the $Service variable.

The second command gets the service template object named ServiceTemplate02 and stores the object in the $SvcTemplate variable.

The third command creates a new release of the service template stored in $SvcTemplate, names it ServiceTemplate02, gives it a release of RTM and stores the template in $PendingTemplate.

The fourth command gets the computer tier object named Web Tier for the service template stored in $PendingTemplate and stores the object in the $WebTier variable.

The fifth command adds memory to the virtual machine template for the computer tier stored in $WebTier.

The sixth command gets the virtual hard disk object named Win2k8R2BaseDisk_Patched.vhd and stores the object in the $BaseDisk2 variable.
This virtual hard disk contains an updated version of the operating system.

The seventh command gets the virtual disk drive object on the virtual machine template stored in $WebTemplate and stores the object in the $VHD variable.

The eighth command removes the virtual disk drive object stored in $VHD.

The ninth command adds the virtual hard disk object stored in $BaseDisk2 to the virtual machine template object stored in $WebTemplate.

The tenth command sets the pending template on the service instance to the updated service template stored in $PendingTemplate.

The last command updates Service02.

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

### -ShowActions
Displays all servicing and orchestration actions that will be performed.
This parameter is useful for debugging.

```yaml
Type: SwitchParameter
Parameter Sets: Service
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
Parameter Sets: WhatIf
Aliases: 

Required: True
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
* Requires a VMM service object, which can be retrieved using the Get-SCService cmdlet.

## RELATED LINKS

[Get-SCService](xref:VirtualMachineManager/v1/Get-SCService.md)

[New-SCService](xref:VirtualMachineManager/v1/New-SCService.md)

[Read-SCService](xref:VirtualMachineManager/v1/Read-SCService.md)

[Remove-SCService](xref:VirtualMachineManager/v1/Remove-SCService.md)

[Resume-SCService](xref:VirtualMachineManager/v1/Resume-SCService.md)

[Set-SCService](xref:VirtualMachineManager/v1/Set-SCService.md)

[Start-SCService](xref:VirtualMachineManager/v1/Start-SCService.md)

[Stop-SCService](xref:VirtualMachineManager/v1/Stop-SCService.md)

[Suspend-SCService](xref:VirtualMachineManager/v1/Suspend-SCService.md)

