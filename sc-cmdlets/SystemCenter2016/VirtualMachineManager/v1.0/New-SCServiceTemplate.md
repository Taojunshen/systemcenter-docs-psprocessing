---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceTemplate.md
schema: 2.0.0
ms.assetid: EF0E8036-30F3-4CA9-A9DD-6C8F253411EE
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCServiceTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCServiceTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/New-SCServiceTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCServiceTemplate

## SYNOPSIS
Creates a service template used to create a service in VMM.

## SYNTAX

```
New-SCServiceTemplate [-Name] <String> [-Description <String>] [-Owner <String>] -Release <String>
 [-UseAsDefaultRelease <Boolean>] [-VMMServer <ServerConnection>] [-UserRole <UserRole>]
 [-ServicePriority <ServicePriority>] [-ServiceTemplate <ServiceTemplate>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCServiceTemplate** cmdlet creates a service template that is used to create a service in Virtual Machine Manager (VMM).
A service template is a description of a service that contains a set of service templates which describe how the service should be deployed, configured, and serviced.
Service templates are stored in the VMM library.

## EXAMPLES

### Example 1: Create a service template
```
PS C:\>$SvcTemplate = New-SCServiceTemplate -Name "ServiceTemplate01" -Release "Beta" -Description "Service Template 01" -Owner "Contoso\Katarina" 
PS C:\> $SvcTemplate
```

The first command creates a service template object named ServiceTemplate01 and stores the object in the $SvcTemplate variable.

The second command displays information about the service template object to the user.

### Example 2: Clone a service template
```
PS C:\>$SvcTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01" | where { $_.Release -eq "Beta" }
PS C:\> $NewSvcTemplate = New-SCServiceTemplate -Name "ServiceTemplate01" -Release "v1" -ServiceTemplate $SvcTemplate
PS C:\> $NewSvcTemplate
```

The first command gets the service template object named ServiceTemplate01 with a release of Beta and stores the object in the $SvcTemplate variable.

The second command creates a clone of ServiceTemplate01 and gives it a release value of v1.
The command then stores the service template object in the $NewSvcTemplate variable.

The last command displays information about the cloned service template object to the user.

## PARAMETERS

### -Description
Specifies a description for the service template.

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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account.

Example format: `-Owner "Contoso\PattiFuller"`
Example format: ` -Owner "PattiFuller@Contoso"`

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

### -Release
Specifies a string that describes the release of a library resource.
VMM automatically creates a release value for every resource imported into the library.
After the resource has been imported, you can customize the string.

```yaml
Type: String
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

### -ServicePriority
Specifies the priority for a service.
Valid values are: Normal, Low, High.
Default value: Normal.

```yaml
Type: ServicePriority
Parameter Sets: (All)
Aliases: 
Accepted values: Normal, Low, High

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UseAsDefaultRelease
Indicates whether this release is used as the default release for the service template.

```yaml
Type: Boolean
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

### ServiceTemplate
This cmdlet returns a **ServiceTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceTemplate.md)

[Read-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Read-SCServiceTemplate.md)

[Remove-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCServiceTemplate.md)

[Resolve-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Resolve-SCServiceTemplate.md)

[Set-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCServiceTemplate.md)

[Test-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Test-SCServiceTemplate.md)

