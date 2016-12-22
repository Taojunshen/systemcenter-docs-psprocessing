---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9FB848F1-8826-44F5-92B0-EE8233194E5D
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSharedResource.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSharedResource.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSharedResource.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSharedResource

## SYNOPSIS
Gets resources that are shared with a self-service user or a self-service user role.

## SYNTAX

```
Get-SCSharedResource [-VMMServer <ServerConnection>] [-UserName <NTAccount>] [-UserRole <UserRole>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSharedResource** cmdlet gets resources that are shared with a self-service user or a self-service user role.

## EXAMPLES

### Example 1: Get all resources that are shared with a specific self-service user
```
PS C:\> Get-SCSharedResource -UserName "Contoso\Daugherty"
```

This command returns all resources that are shared to the user named Daugherty.

### Example 2: Get all resources that are shared with a specific self-service user role
```
PS C:\> $Role = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> Get-SCSharedResource -UserRole $Role
```

The first command gets the user role object named ContosoSelfServiceUsers, and then stores that object in the $Role variable.

The second command returns the resources that are shared to the user role stored in $Role.

### Example 3: Get all resources that are shared with a specific user in a specific user role
```
PS C:\> $Role = Get-SCUserRole -Name "ContosoSelfServiceUsers"
PS C:\> Get-SCSharedResource -UserName "Contoso\Daugherty" -UserRole $Role
```

The first command gets the user role object named ContosoSelfServiceUsers, and then stores that object in the $Role variable.

The second command returns the resources that are shared with the user named Daugherty in the user role stored in $Role.

## PARAMETERS

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

### -UserName
Specifies a the name of a user.
Enter a user name in the format Domain\User.

```yaml
Type: NTAccount
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

### SharedResource
This cmdlet returns a **SharedResource** object.

## NOTES

## RELATED LINKS

[Get-SCUserRole](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUserRole.md)

[Grant-SCResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Grant-SCResource.md)

[Revoke-SCResource](xref:SystemCenter2016/VirtualMachineManager/vlatest/Revoke-SCResource.md)

