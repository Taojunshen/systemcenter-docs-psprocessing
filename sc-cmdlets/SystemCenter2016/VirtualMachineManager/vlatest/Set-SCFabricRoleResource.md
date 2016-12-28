---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E1D65222-822F-49E9-8CCA-211790D93F40
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRoleResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRoleResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCFabricRoleResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCFabricRoleResource

## SYNOPSIS
Modifies a fabric role resource.

## SYNTAX

```
Set-SCFabricRoleResource [-VMMServer <ServerConnection>] [-FabricRoleResource] <FabricRoleResource>
 [-RunAsAccount <RunAsAccount>] [-NCBGPRouter <NCBGPRouter>] [-Recursive] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCFabricRoleResource** cmdlet modifies a fabric role resource.

## EXAMPLES

### Example 1: Set the configuration of fabric resources
```
PS C:\> $NetworkService = Get-SCNetworkService -Name "ns"
PS C:\> $FabricRole = Get-SCFabricRole -NetworkService $NetworkService -Name "fr"
PS C:\> $VirtualMachine = Get-SCVirtualMachine -Name "VM01"
PS C:\> $VmFabricRoleResource = $FabricRole.ServiceVMs | where { $_.Resource -eq $VirtualMachine }
PS C:\> $BgpPeers = @()
PS C:\> $BgpPeers += New-SCNCBGPPeer -RouterName "BGPPEER" -RouterIPAddress "10.20.30.40" -RouterAsn 60
PS C:\> $BgpRouter = New-SCNCBGPRouter -LocalASN 30 -RouterPeers $BgpPeers
PS C:\> Set-SCFabricRoleResource -FabricRoleResource $VmFabricRoleResource -NCBGPRouter $BgpRouter
```

The first command gets a network service by using the **Get-SCNetworkService** cmdlet, and then stores it in the $NetworkService variable.

The second command gets a fabric role for the service in $NetworkService by using the **Get-SCFabricRole** cmdlet, and then stores it in the $FabricRole variable.

The third command gets a virtual machine named VM01 by using the **Get-SCVirtualMachine** cmdlet, and then stores it in the $VirtualMachine variable.

The fourth command gets a specified service, and stores that resource in the $ServiceFabricRoleResource variable.

The fifth command creates an array variable named $BgpPeers.

The sixth command creates a peer by using the **New-SCNCBGPPeer** cmdlet, and then adds it to $BgpPeers.

The seventh command creates a router object by using the **New-SCNCBGPRouter** cmdlet based on the value of $BgpPeers.
The command stores the result in the $BgpRouter variable.

The final command updates the settings based on $BgpRouter the specified fabric resource.

## PARAMETERS

### -FabricRoleResource
Specifies the fabric role resource to modify.

```yaml
Type: FabricRoleResource
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -NCBGPRouter


```yaml
Type: NCBGPRouter
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

### -Recursive


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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

```yaml
Type: RunAsAccount
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCFabricRoleResource.md)

[Get-SCFabricRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCFabricRole.md)

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNetworkService.md)

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[New-SCNCBGPPeer](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPPeer.md)

[New-SCNCBGPRouter](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCNCBGPRouter.md)

[Remove-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCFabricRoleResource.md)

