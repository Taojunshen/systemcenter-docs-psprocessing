---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 9D28D7CD-9B2A-4B73-80C9-57F8DC32746C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationHostTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationHostTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCApplicationHostTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCApplicationHostTemplate

## SYNOPSIS
Adds an application host template to a service template.

## SYNTAX

### DefaultParamSet (Default)
```
Add-SCApplicationHostTemplate [-DeploymentOrder <Int32>] [-ServicingOrder <Int32>] [-Name] <String>
 [-Description <String>] [-Tag <String>] -ComputerName <String> -ApplicationProfile <ApplicationProfile>
 -ServiceTemplate <ServiceTemplate> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### WebApplicationHost
```
Add-SCApplicationHostTemplate [-DeploymentOrder <Int32>] [-ServicingOrder <Int32>] [-Port <Int32>]
 [-AllowUntrustedServerCertificate <Boolean>] -RunAsAccount <VMMCredential> [-WebApplicationHost]
 [-Name] <String> [-Description <String>] [-Tag <String>] -ComputerName <String> -Site <String>
 [-AuthenticationType <String>] -ApplicationProfile <ApplicationProfile> -ServiceTemplate <ServiceTemplate>
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCApplicationHostTemplate** cmdlet adds an application host template to a service template.
An application host template is used to deploy a SQL data-tier application (DAC) on a deployed SQL server or a Web Deploy package to a supported Web Application Host.

## EXAMPLES

### Example 1: Add a SQL application host template to a service template
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "SvcWebAppProfile01"
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> Add-SCApplicationHostTemplate -Name "SQL Application Host" -ComputerName "SQLServer01.Contoso.com" -ApplicationProfile $AppProfile -ServiceTemplate $ServiceTemplate
```

The first command gets the aplication profile object named SvcWebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the service temnplate object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The third command adds an application host template to the service template stored in $ServiceTemplate.

### Example 2: Add a web application host template to a service template
```
PS C:\> $AppProfile = Get-SCApplicationProfile -Name "WebAppProfile01"
PS C:\> $ServiceTemplate = Get-SCServiceTemplate -Name "ServiceTemplate01"
PS C:\> $WebRAA = Get-SCRunAsAccount -Name "IIS Site Admin"
PS C:\> $WebAppHostTemplate = Add-SCApplicationHostTemplate -Name "Web Farm" -ServiceTemplate $ServiceTemplate -ApplicationProfile -$AppProfile -ComputerName "@Web Server@" -DeploymentOrder 2 -WebAppHost -Port 8172 -Site "Default Web Site" -AuthenticationType "NTLM" -AllowUntrustedServerCertificate -RunAsAccount $WebRAA
```

The first command gets the aplication profile object named WebAppProfile01 and stores the object in the $AppProfile variable.

The second command gets the service template object named ServiceTemplate01 and stores the object in the $ServiceTemplate variable.

The third command gets the Run As Account object named IIS Site Admin and stores the object in the $WebRAA variable.

The last command adds a web application host template to the service template stored in $ServiceTemplate (in this case, ServiceTemplate01).

## PARAMETERS

### -AllowUntrustedServerCertificate
Indicates whether the deployment may proceed when the target deployment server presents an untrusted server certificate.
This parameter is used in conjunction with a Web Application host template.

```yaml
Type: Boolean
Parameter Sets: WebApplicationHost
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ApplicationProfile
Specifies an application profile object.

```yaml
Type: ApplicationProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AuthenticationType
Specifies the authentication mechanism used to facilitate the deployment of web applications associated with the template.
This parameter is used in conjunction with a Web Application host template.
Valid values are: NTLM and Basic.

```yaml
Type: String
Parameter Sets: WebApplicationHost
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

Required: True
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

Required: True
Position: 0
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
Parameter Sets: WebApplicationHost
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
Parameter Sets: WebApplicationHost
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

### -ServiceTemplate
Specifies a service template object.

```yaml
Type: ServiceTemplate
Parameter Sets: (All)
Aliases: 

Required: True
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
Parameter Sets: WebApplicationHost
Aliases: 

Required: True
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

### -WebApplicationHost
Specifies that the application host template is used for a Web Application Host.

```yaml
Type: SwitchParameter
Parameter Sets: WebApplicationHost
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

### ApplicationHostTemplate
This cmdlet returns an **ApplicationHostTemplate** object.

## NOTES

## RELATED LINKS

[Get-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationHostTemplate.md)

[Get-SCApplicationProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCApplicationProfile.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCServiceTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCServiceTemplate.md)

[Remove-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCApplicationHostTemplate.md)

[Set-SCApplicationHostTemplate](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCApplicationHostTemplate.md)

