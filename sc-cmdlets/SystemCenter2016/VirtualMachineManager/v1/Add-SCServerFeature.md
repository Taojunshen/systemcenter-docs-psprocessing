---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCGuestOSProfile.md
schema: 2.0.0
ms.assetid: 40DC6D06-F50F-4B68-8172-D046290C4911
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCServerFeature.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCServerFeature.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Add-SCServerFeature.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCServerFeature

## SYNOPSIS
Adds an operating system role or feature to a guest operating system profile.

## SYNTAX

### OSProfile
```
Add-SCServerFeature [-VMMServer <ServerConnection>] -ServerFeature <ServerFeature>
 -GuestOSProfile <GuestOSProfile> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### Template
```
Add-SCServerFeature [-VMMServer <ServerConnection>] -ServerFeature <ServerFeature> -VMTemplate <Template>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCServerFeature** cmdlet adds an operating system role or feature to a guest operating system profile.
The role or feature is automatically installed during machine deployment and servicing operations.

## EXAMPLES

### Example 1: Add a server feature to a guest operating system profile
```
PS C:\>$OSProfile = Get-SCGuestOSProfile -Name "NewOSProfile01"
PS C:\> $Feature = Get-SCServerFeature -Name "Failover-Clustering"
PS C:\> Add-SCServerFeature -GuestOSProfile $OSProfile -ServerFeature $Feature
```

The first command gets the guest operating system profile object named NewOSProfile01 and stores the object in the $OSProfile variable.

The second command gets the server feature object named Failover-Clustering and stores the object in the $Feature variable.

The last command adds the server feature stored in $Feature (Failover-Clustering) to the guest operating system profile stored in $OSProfile (NewOSProfile01).

## PARAMETERS

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
Parameter Sets: OSProfile
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

### -ServerFeature
Specifies a server feature object.

```yaml
Type: ServerFeature
Parameter Sets: (All)
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

### -VMTemplate
Specifies a VMM template object used to create virtual machines.

```yaml
Type: Template
Parameter Sets: Template
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

### ServerFeature
This cmdlet returns a **ServerFeature** object.

## NOTES

## RELATED LINKS

[Get-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCGuestOSProfile.md)

[Get-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServerFeature.md)

[Remove-SCServerFeature](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCServerFeature.md)

