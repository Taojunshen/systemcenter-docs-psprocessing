---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCServiceSetting.md
schema: 2.0.0
ms.assetid: 9D3C628F-E468-4E36-9034-C767821C8D60
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCServiceSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCServiceSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Set-SCServiceSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCServiceSetting

## SYNOPSIS
Modifies a service setting.

## SYNTAX

### Value (Default)
```
Set-SCServiceSetting [-Value <String>] [-VMMServer <ServerConnection>] [-ServiceSetting] <ServiceSetting>
 [-Description <String>] [-IsRequired <Boolean>] [-IsEncrypted <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>]
 [<CommonParameters>]
```

### SecureValue
```
Set-SCServiceSetting [-SecureValue <SecureString>] [-VMMServer <ServerConnection>]
 [-ServiceSetting] <ServiceSetting> [-Description <String>] [-IsRequired <Boolean>] [-IsEncrypted <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCServiceSetting** cmdlet modifies a service setting.

## EXAMPLES

### Example 1: Make a service setting mandatory
```
PS C:\>$Template = Get-SCServiceTemplate -Name "ServiceTemplate01" | where {$_.Release -eq "Beta"}
PS C:\> $ServiceSetting = Get-SCServiceSetting -ServiceTemplate $Template -Name "Setting01"
PS C:\> Set-SCServiceSetting -ServiceSetting $ServiceSetting -IsRequired $True
```

The first command gets the service template object named ServiceTemplate01 with a release of Beta and stores the object in the $ServiceTemplate variable.

The second command gets the service setting object named Setting01 from ServiceTemplate01 and stores the object in the $ServiceSetting variable.

The last command modifies the service setting so that it is mandatory.

## PARAMETERS

### -Description
Specifies a description for the service setting.

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

### -IsEncrypted
Indicates whether a service setting is encrypted.

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

### -IsRequired
Indicates whether a service setting is mandatory.

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

### -SecureValue
Specifies the value for a secure string.

```yaml
Type: SecureString
Parameter Sets: SecureValue
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceSetting
Specifies a service setting object.

```yaml
Type: ServiceSetting
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

### -Value
Specifies a string used to attribute an object or property.

```yaml
Type: String
Parameter Sets: Value
Aliases: 

Required: False
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

[Get-SCServiceSetting](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServiceSetting.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCServiceTemplate.md)

