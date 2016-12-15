---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVMSubnet.md
schema: 2.0.0
ms.assetid: 4FDA1A53-ADFF-4BC7-9F71-8B6C54E6F214
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMSubnet.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMSubnet.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMSubnet.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVMSubnet

## SYNOPSIS
Modifies a virtual machine subnet.

## SYNTAX

```
Set-SCVMSubnet [-VMMServer <ServerConnection>] [-VMSubnet] <VMSubnet> [-Name <String>] [-Description <String>]
 [-SubnetVLan <SubnetVLan[]>] [-MaxNumberOfPorts <UInt32>] [-RemoveMaxNumberOfPorts] [-PortACL <PortACL>]
 [-RemovePortACL] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMSubnet** cmdlet modifies the properties of a virtual machine subnet.

To get a virtual machine subnet object to update, use the Get-SCVMSubnet cmdlet.

For more information about virtual machine subnets, type `Get-Help New-SCVMSubnet -Detailed`.

## EXAMPLES

### Example 1: Change the subnet VLan for a virtual machine subnet
```
PS C:\>$SubnetVLan = New-SCSubnetVLan -Subnet "192.168.4.0/24"
PS C:\> Get-SCVMSubnet -Name "VMSubnet01" | Set-SCVMSubnet -SubnetVLan $SubNetVLan
```

The first command creates a subnet VLan object and stores the object in the $SubnetVLan variable.

The second command gets the virtual machine subnet object named VMSubnet01 and uses the pipeline operator to pass the object to Set-SCVMSubnet which updates its subnet VLan to 192.168.4.0/24.

## PARAMETERS

### -Description
Specifies a description for the virtual machine subnet.

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

### -MaxNumberOfPorts
Specifies the maximum number of ports supported by the virtual machine subnet.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -PortACL
Specifies a port access control list (ACL).

```yaml
Type: PortACL
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveMaxNumberOfPorts
Removes the value set on the virtual machine subnet for the maximum number of ports supported by the virtual machine subnet.

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

### -RemovePortACL
Indicates that this operation removes the port ACL.

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

### -SubnetVLan
Specifies one or more IP subnet and VLAN sets.

For information about creating a **SubnetVLan** object, type `Get-Help New-SCSubNetVLan`.

```yaml
Type: SubnetVLan[]
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

### -VMSubnet
Specifies a virtual machine subnet object.

To obtain a **VMSubnet** object, use the Get-SCVMSubnet cmdlet.

```yaml
Type: VMSubnet
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

[Get-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMSubnet.md)

[New-SCSubnetVLan](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCSubnetVLan.md)

[New-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMSubnet.md)

[Remove-SCVMSubnet](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMSubnet.md)

