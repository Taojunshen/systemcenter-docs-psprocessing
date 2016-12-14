---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCApplicationDeployment.md
schema: 2.0.0
ms.assetid: F48B99A8-88C2-4EAE-A3C7-DC036EB9123A
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationSetting.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationSetting.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationSetting.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCApplicationSetting

## SYNOPSIS
Sets the value of an application setting.

## SYNTAX

### Value (Default)
```
Set-SCApplicationSetting [-VMMServer <ServerConnection>] [-ApplicationSetting] <ApplicationSetting>
 [-Value <String>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### SecureValue
```
Set-SCApplicationSetting [-VMMServer <ServerConnection>] [-ApplicationSetting] <ApplicationSetting>
 [-SecureValue <SecureString>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCApplicationSetting** cmdlet sets the value of an application setting.

## EXAMPLES

### Example 1: Set the value for an application setting
```
PS C:\>$AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $AppDeployment = Get-SCApplicationDeployment -ApplicationProfile $AppProfile -Name "SvcWebDeployment01"
PS C:\> $AppSetting = Get-SCApplicationSetting -ApplicationDeployment $AppDeployment -Name "Order_Service"
PS C:\> Set-SCApplicationSetting -ApplicationSetting $AppSetting -Value "http://@servicesComputerName@/OrderService.xamlx"
```

The first command gets the application profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the application deployment object named SvcWebDeployment01 for the application profile stored in $AppProfile and stores the object in the $AppDeployment variable.

The third command gets the setting object named Order_Service for the application package in the application deployment stored in $AppDeployment, and then stores the setting object in the $AppSetting variable.

The last command sets the value for the application setting stored in $AppSetting.
In this case, the value for the Order_Service setting was updated in the SvcWebDeployment01 application deployment.

## PARAMETERS

### -ApplicationSetting
Specifies an application setting object.

```yaml
Type: ApplicationSetting
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### ApplicationSetting
This cmdlet returns an **ApplicationSetting** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationDeployment](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationDeployment.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationProfile.md)

[Get-SCApplicationSetting](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationSetting.md)

