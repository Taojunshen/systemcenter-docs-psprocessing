---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 21F6C360-894E-4DF0-B6B6-EF0A3CFCAAC5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Resume-SCService.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Resume-SCService

## SYNOPSIS
Starts a paused VMM service and all virtual machines within that service.

## SYNTAX

```
Resume-SCService [-VMMServer <ServerConnection>] [-Service] <Service> [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Resume-SCService** cmdlet starts a paused Virtual Machine Manager (VMM) service and all virtual machines within that service.
To pause a service use the **Suspend-SCService** cmdlet.

## EXAMPLES

### Example 1: Resume a specific service
```
PS C:\> $Service = Get-SCService -Name "Service01"
PS C:\> Resume-SCService -Service $Service
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command resumes the service stored in $Service, which resumes all of the virtual machines in the service.

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

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

[New-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCService.md)

[Read-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCService.md)

[Remove-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCService.md)

[Set-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCService.md)

[Start-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Start-SCService.md)

[Stop-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Stop-SCService.md)

[Suspend-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Suspend-SCService.md)

[Update-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Update-SCService.md)

