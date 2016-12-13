---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCService.md
schema: 2.0.0
ms.assetid: 37E31EF8-50F6-4DF4-AE6B-D8EF5600DFE8
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Start-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Start-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Start-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Start-SCService

## SYNOPSIS
Starts a VMM service and all virtual machines within the service.

## SYNTAX

```
Start-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Start-SCService** cmdlet starts a Virtual Machine Manager (VMM) service and all virtual machines within the service.
To stop a service, use the Stop-SCService cmdlet.

## EXAMPLES

### Example 1: Start a specified service
```
PS C:\>$Service = Get-SCService -Name "Service01"
PS C:\> Start-SCService -Service $Service
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command starts the service in $Service, which starts all of the virtual machines in the service.

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

[Get-SCService](xref:VirtualMachineManager/v1/Get-SCService.md)

[New-SCService](xref:VirtualMachineManager/v1/New-SCService.md)

[Read-SCService](xref:VirtualMachineManager/v1/Read-SCService.md)

[Remove-SCService](xref:VirtualMachineManager/v1/Remove-SCService.md)

[Resume-SCService](xref:VirtualMachineManager/v1/Resume-SCService.md)

[Set-SCService](xref:VirtualMachineManager/v1/Set-SCService.md)

[Stop-SCService](xref:VirtualMachineManager/v1/Stop-SCService.md)

[Suspend-SCService](xref:VirtualMachineManager/v1/Suspend-SCService.md)

[Update-SCService](xref:VirtualMachineManager/v1/Update-SCService.md)

