---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCApplicationHostTemplate.md
schema: 2.0.0
ms.assetid: 41C42EBA-A9ED-4E7C-BBE0-7E385DAA0186
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationHostTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationHostTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Set-SCApplicationHostTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCApplicationHostTemplate

## SYNOPSIS
Configures the properties of an application host template that has been added to a service template.

## SYNTAX

```
Set-SCApplicationHostTemplate [-DeploymentOrder <Int32>] [-ServicingOrder <Int32>] [-Port <Int32>]
 [-AllowUntrustedServerCertificate <Boolean>] [-RunAsAccount <VMMCredential>]
 [-ApplicationHostTemplate] <ApplicationHostTemplate> [-Name <String>] [-Description <String>]
 [-Owner <String>] [-Tag <String>] [-ComputerName <String>] [-Site <String>] [-AuthenticationType <String>]
 [-ApplicationProfile <ApplicationProfile>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCApplicationHostTemplate** cmdlet configures the properties of an application host template that has been added to a service template.

## EXAMPLES

### Example 1: Change the description of the application host template
```
PS C:\>$ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $AppHostTemplate = Get-SCApplicationHostTemplate -ServiceTemplate $ServiceTemplate
PS C:\> Set-SCApplicationHostTemplate -ApplicationHostTemplate $AppHostTemplate -Description "This is the updated description"
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the application host template object for the service template in $ServiceTemplate and stores the object in the $AppHostTemplate variable.

The last command changes the description property of the application host template in $AppHostTemplate.

### Example 2: Change the name of an application host template
```
PS C:\>$ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $AppHostTemplate = Get-SCApplicationHostTemplate -ServiceTemplate $ServiceTemplate
PS C:\> Set-SCApplicationHostTemplate -ApplicationHostTemplate $AppHostTemplate -Name "This is the updated name"
```

The first command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The second command gets the application host template object for the service template stored in $ServiceTemplate and stores the object in the $AppHostTemplate variable.

The last command changes the name property of the application host template stored in $AppHostTemplate.
Because the application host template is cloned into the service template, renaming the application host template does not affect other service templates in the system.

## PARAMETERS

### -AllowUntrustedServerCertificate
Indicates whether the deployment may proceed when the target deployment server presents an untrusted server certificate.
This parameter is used in conjunction with a Web Application host template.

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

### -ApplicationHostTemplate
Specifies an application host template object.

```yaml
Type: ApplicationHostTemplate
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthenticationType
Specifies the authentication mechanism used to facilitate the deployment of web applications associated with the template.
This parameter is used in conjunction with a Web Application host template.
Valid values are: NTLM and Basic.

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

### -ComputerName
Specifies the name of a computer that Virtual Machine Manager (VMM) can uniquely identify on your network.
Valid formats are: 

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### -DeploymentOrder
Specifies the order in which a computer tier, application host, or application is deployed.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the application host template.

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

Required: False
Position: Named
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

### -Port
Specifies the network port to use when adding an object or creating a connection.
Valid values are: 1 to 4095.

```yaml
Type: Int32
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
Type: VMMCredential
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

### -ServicingOrder
Specifies the order in which a computer tier or application host is serviced.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Site
Specifies the web site to which any associated web deploy packages are deployed.
This parameter is used in conjunction with a Web Application host template.

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

### -Tag
Specifies a word or phrase to associate with an object so that you can search for all objects with the specified set of tags.
You can search for a subset of tags, or you can search for the full set of tags.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### ApplicationHostTemplate
This cmdlet returns an **ApplicationHostTemplate** object.

## NOTES

## RELATED LINKS

[Add-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCApplicationHostTemplate.md)

[Get-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCApplicationHostTemplate.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCServiceTemplate.md)

[Remove-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCApplicationHostTemplate.md)

