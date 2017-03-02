---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 38A54E92-08FA-479E-A9BE-33E6D2030D11
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServicingWindow.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCServicingWindow

## SYNOPSIS
Gets a list of servicing windows that are assigned to a virtual machine, a host, or a service.

## SYNTAX

### Connection (Default)
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] [<CommonParameters>]
```

### FromName
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] [-Name] <String> [<CommonParameters>]
```

### FromID
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

### FromVMHost
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] [-ServicingWindowFilter <ServicingWindowFilterType>]
 -VMHost <Host> [<CommonParameters>]
```

### FromVM
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] [-ServicingWindowFilter <ServicingWindowFilterType>]
 -VM <VM> [<CommonParameters>]
```

### FromService
```
Get-SCServicingWindow [-VMMServer <ServerConnection>] [-ServicingWindowFilter <ServicingWindowFilterType>]
 -Service <Service> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCServicingWindow** cmdlet gets a list of servicing windows that are assigned to a virtual machine, a host, or a service.

## EXAMPLES

### Example 1: Get a specific servicing window by its name
```
PS C:\> $SvcWindow = Get-SCServicingWindow -Name "Backup Staging A"
PS C:\> $SvcWindow
```

The first command gets the servicing window object named Backup Staging A and stores the object in the $SvcWindow variable.

The second command displays the information about the servicing window stored in $SvcWindow (Backup Staging A).

## PARAMETERS

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: FromID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

```yaml
Type: String
Parameter Sets: FromName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Service
Specifies a VMM service object.

```yaml
Type: Service
Parameter Sets: FromService
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServicingWindowFilter
Specifies a filter for retrieving servicing windows.
Valid values are: 

- Now
- Next
- All

```yaml
Type: ServicingWindowFilterType
Parameter Sets: FromVMHost, FromVM, FromService
Aliases: 
Accepted values: Now, Next, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: FromVM
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the **Add-SCVMHost** cmdlet.

```yaml
Type: Host
Parameter Sets: FromVMHost
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

### ServicingWindow
This cmdlet returns a **ServicingWindow** object.

## NOTES

## RELATED LINKS

[New-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCServicingWindow.md)

[Remove-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCServicingWindow.md)

[Set-SCServicingWindow](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCServicingWindow.md)

