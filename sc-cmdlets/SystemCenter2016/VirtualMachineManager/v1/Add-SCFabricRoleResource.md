---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCFabricRole.md
schema: 2.0.0
ms.assetid: D4E767B4-B896-4A0E-8521-9AF142C720CD
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCFabricRoleResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCFabricRoleResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCFabricRoleResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCFabricRoleResource

## SYNOPSIS
Adds a fabric role resource.

## SYNTAX

### VMResource (Default)
```
Add-SCFabricRoleResource [-VMMServer <ServerConnection>] [-FabricRole] <FabricRole> -VirtualMachine <VM>
 -RunAsAccount <RunAsAccount> [-IPv4Subnet <SubnetVLan>] [-BackEndSwitchName <String>]
 [-FrontEndSwitchName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### ServiceResource
```
Add-SCFabricRoleResource [-VMMServer <ServerConnection>] [-FabricRole] <FabricRole> -ServiceInstance <Service>
 -RunAsAccount <RunAsAccount> [-IPv4Subnet <SubnetVLan>] [-BackEndSwitchName <String>]
 [-FrontEndSwitchName <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCFabricRoleResource** cmdlet adds a fabric role resource.

## EXAMPLES

### Example 1: Add fabric role resource to a fabric role
```
PS C:\>$NetworkService = Get-SCNetworkService -Name "ns"
PS C:\> $FabricRole = Get-SCFabricRole -NetworkService $NetworkService -Name "fr"
PS C:\> $VirtualMachine = Get-SCVirtualMachine -Name "VM01"
PS C:\> $RunAsAccount = Get-SCRunAsAccount -Name "ContosoAccount"
PS C:\> $SubnetVlanIPv4 = New-SCSubnetVLan -Subnet "10.185.108.0/23" -VLanID "564"
PS C:\> Add-SCFabricRoleResource -FabricRole $FabricRole -VirtualMachine $VirtualMachine -IPv4Subnet $SubnetVlanIPv4 -RunAsAccount $RunAsAccount"
```

The first command gets a network service by using the Get-SCNetworkService cmdlet, and then stores it in the $NetworkService variable.

The second command gets a fabric role for the service in $NetworkService by using the Get-SCFabricRole, and then stores it in the $FabricRole variable.

The third command gets a virtual machine named VM01 by using the Get-SCVirtualMachine cmdlet, and then stores it in the $VirtualMachine variable.

The fourth command gets the run as account named ContosoAccount by using the Get-SCRunAsAccount, and then stores it in the $RunAsAccount variable.

The fifth command creates a virtual LAN by using the New-SCSubnetVLan cmdlet, and then stores it in the $SubnetVlanIPv4 variable.

The final command adds the new fabric role resource to the fabric role in $FabricRole.
The command specifies the values created by previous commands in the example.

## PARAMETERS

### -BackEndSwitchName
Specifies the name of a back-end switch.

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

### -FabricRole
Specifies a fabric role.

```yaml
Type: FabricRole
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontEndSwitchName
Specifies the name of a front-end switch.

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

### -IPv4Subnet


```yaml
Type: SubnetVLan
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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
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

### -ServiceInstance
Specifies a service object.

```yaml
Type: Service
Parameter Sets: ServiceResource
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

### -VirtualMachine
Specifies a virtual machine object.

```yaml
Type: VM
Parameter Sets: VMResource
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

## NOTES

## RELATED LINKS

[Get-SCFabricRole](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCFabricRole.md)

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCNetworkService.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[New-SCSubnetVLan](xref:SystemCenter2016/VirtualMachineManager/v1/New-SCSubnetVLan.md)

[Remove-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCFabricRoleResource.md)

[Set-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCFabricRoleResource.md)

