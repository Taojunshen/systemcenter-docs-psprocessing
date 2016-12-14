---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCFabricRoleResource.md
schema: 2.0.0
ms.assetid: A7F79280-F09C-49B5-A365-C81A7862AFFC
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCFabricRoleResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCFabricRoleResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Remove-SCFabricRoleResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCFabricRoleResource

## SYNOPSIS
Removes a fabric role resource.

## SYNTAX

```
Remove-SCFabricRoleResource [-VMMServer <ServerConnection>] [-FabricResource] <FabricRoleResource> [-Force]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCFabricRoleResource** cmdlet removes a fabric role resource.

## EXAMPLES

### Example 1: Remove a fabric role resource
```
PS C:\>$NetworkService = Get-SCNetworkService -Name "ns"
PS C:\> $FabricRole = Get-SCFabricRole -NetworkService $NetworkService -Name "fr"
PS C:\> $ServiceFabricRoleResource = $FabricRole.Services | where { $_.ID -eq "775aaefb-1df1-408d-bd1f-e9ffe64c14ae" }
PS C:\> Remove-SCFabricRoleResource -FabricResource $ServiceFabricRoleResource
```

The first command gets a network service by using the Get-SCNetworkService cmdlet, and then stores it in the $NetworkService variable.

The second command gets a fabric role for the service in $NetworkService by using the Get-SCFabricRole, and then stores it in the $FabricRole variable.

The third command gets a specified service, and stores that resource in the $ServiceFabricRoleResource variable.

The final command removes the resource in $ServiceFabricRoleResource.

## PARAMETERS

### -FabricResource
Specifies the fabric role resource to remove.

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

### -Force
Forces the command to run without asking for user confirmation.

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

[Add-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCFabricRoleResource.md)

[Get-SCFabricRole](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCFabricRole.md)

[Get-SCNetworkService](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCNetworkService.md)

[Set-SCFabricRoleResource](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCFabricRoleResource.md)
