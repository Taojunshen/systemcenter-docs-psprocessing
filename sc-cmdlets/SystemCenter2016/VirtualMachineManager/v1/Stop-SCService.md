---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCService.md
schema: 2.0.0
ms.assetid: 77B3C64D-24E3-4545-B56F-0E23DF3A4AB9
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Stop-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Stop-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Stop-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Stop-SCService

## SYNOPSIS
Stops a VMM service and all virtual machines within the service.

## SYNTAX

### Default (Default)
```
Stop-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### Shutdown
```
Stop-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-Shutdown] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### DiscardSavedState
```
Stop-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-DiscardSavedState] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### SaveState
```
Stop-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-SaveState] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-SCService** cmdlet stops a Virtual Machine Manager (VMM) service and all virtual machines within the service.
To start a service, use the Start-SCService cmdlet.

## EXAMPLES

### Example 1: Stop a specific service
```
PS C:\> $Service = Get-SCService -Name "Service01"
PS C:\> Stop-SCService -Service $Service
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command stops the service in $Service, which stops all of the virtual machines in the service.

## PARAMETERS

### -DiscardSavedState
Indicates that this cmdlet deletes the saved state associated with a service.

```yaml
Type: SwitchParameter
Parameter Sets: DiscardSavedState
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

### -SaveState
Saves the state of a virtual machine or service.

```yaml
Type: SwitchParameter
Parameter Sets: SaveState
Aliases: 

Required: True
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

### -Shutdown
Indicates that a virtual machine, service, or a source server should be shut down.
In the case of a virtual machine or service, the associated cmdlet attempts to use the operating system to shut the virtual machine down gracefully.

In the case of a successful physical-to-virtual machine (P2V) conversion, the cmdlet shuts down the source server.

```yaml
Type: SwitchParameter
Parameter Sets: Shutdown
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

### VirtualMachine[]
This cmdlet returns an array of **VirtualMachine** objects.

## NOTES

## RELATED LINKS

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCService.md)

[New-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCService.md)

[Read-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCService.md)

[Remove-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCService.md)

[Resume-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Resume-SCService.md)

[Set-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCService.md)

[Start-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Start-SCService.md)

[Suspend-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Suspend-SCService.md)

[Update-SCService](xref:SystemCenter2016/VirtualMachineManager/v1/Update-SCService.md)

