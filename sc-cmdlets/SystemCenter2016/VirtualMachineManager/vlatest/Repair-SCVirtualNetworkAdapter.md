---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 448F0CC0-3790-48C9-A0D1-1C8674F78C51
updated_at: 12/22/2016 11:45 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetworkAdapter.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetworkAdapter.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/69b4a56d68a4e0923028e6be0f8a829d73f2d10b/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-SCVirtualNetworkAdapter.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Repair-SCVirtualNetworkAdapter

## SYNOPSIS
Repairs a virtual network adapter.

## SYNTAX

```
Repair-SCVirtualNetworkAdapter [-VMMServer <ServerConnection>] [-VirtualNetworkAdapter] <VirtualNetworkAdapter>
 [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-SCVirtualNetworkAdapter** cmdlet repairs a virtual network adapter.

## EXAMPLES

### Example 1: Repair a virtual network adapter
```
PS C:\> $VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VirtNetworkAdapter = Get-SCVirtualNetworkAdapter -VM $VM
PS C:\> Repair-SCVirtualNetworkAdapter -VirtualNetworkAdapter $VirtNetworkAdapter[0]
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command gets all virtual network adapter objecte for VM01 and stores the objects in the $VirtNetworkAdapter variable.

The last command repairs the first virtual network adapter stored in $VirtNetworkAdapter.

## PARAMETERS

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -VirtualNetworkAdapter
Specifies a virtual network adapter object for a virtual machine.

Types of hosts support the following number of virtual network adapters: 

- Hyper-V. 
Up to four emulated adapters per virtual machine.
There is no driver available for an emulated network adapter on a Windows Server 2003 x64 guest operating system.

- Hyper-V. 
Up to eight synthetic adapters per virtual machine.
- VMware ESX. 
Up to four emulated adapters per virtual machine.
- Citrix XenServer. 
Up to seven emulated adapters per virtual machine.

```yaml
Type: VirtualNetworkAdapter
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Get-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualNetworkAdapter.md)

[New-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVirtualNetworkAdapter.md)

[Remove-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualNetworkAdapter.md)

[Set-SCVirtualNetworkAdapter](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualNetworkAdapter.md)

