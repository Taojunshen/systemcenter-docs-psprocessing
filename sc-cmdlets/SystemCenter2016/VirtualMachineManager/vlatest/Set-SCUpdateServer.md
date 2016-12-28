---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: F6958BC0-A980-4730-9FDB-E1AA9AA4B1B9
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCUpdateServer

## SYNOPSIS
Configures the settings of a WSUS server that has been added to VMM.

## SYNTAX

### Default (Default)
```
Set-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 [-UpdateLanguages <System.Collections.Generic.List`1[System.String]>]
 [-UpdateCategories <System.Collections.Generic.List`1[System.String]>]
 [-UpdateClassifications <System.Collections.Generic.List`1[System.String]>] [-ProxyCredential <PSCredential>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### ManualSync
```
Set-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 [-UpdateLanguages <System.Collections.Generic.List`1[System.String]>]
 [-UpdateCategories <System.Collections.Generic.List`1[System.String]>]
 [-UpdateClassifications <System.Collections.Generic.List`1[System.String]>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### DisableProxy
```
Set-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 [-UpdateLanguages <System.Collections.Generic.List`1[System.String]>]
 [-UpdateCategories <System.Collections.Generic.List`1[System.String]>]
 [-UpdateClassifications <System.Collections.Generic.List`1[System.String]>] [-DisableProxy]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### EnableProxy
```
Set-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 [-UpdateLanguages <System.Collections.Generic.List`1[System.String]>]
 [-UpdateCategories <System.Collections.Generic.List`1[System.String]>]
 [-UpdateClassifications <System.Collections.Generic.List`1[System.String]>] [-EnableProxy]
 -ProxyServerName <String> -ProxyServerPort <UInt32> -IsProxyAccessAnonymous <Boolean>
 [-ProxyCredential <PSCredential>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### ConfigSettingsChange
```
Set-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 -AllowConfigurationChanges <Boolean> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCUpdateServer** cmdlet configures a Microsoft Windows Server Update Services (WSUS) server that has been added to Virtual Machine Manager (VMM).
For information about how to add a WSUS server to VMM, type `Get-Help Add-SCUpdateServer`.

## EXAMPLES

### Example 1: Enable the proxy setting on an update server
```
PS C:\> $UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
PS C:\> $Categories = @("SQL Server", "Windows")
PS C:\> $Classifications = @("Security Updates", "Service Packs")
PS C:\> $Languages = @("en", "pt-br") 
PS C:\> Set-SCUpdateServer -UpdateServer $UpdateServer -EnableProxy -ProxyServerName "proxy.contoso.com" -ProxyServerPort "88" -IsProxyAccessAnonymous $True -UpdateCategories $Categories -UpdateClassifications $Classifications -UpdateLanguages $Languages
```

The first command gets the update server named WSUSComputer01, and then stores that object in the $UpdateServer variable.

The second command creates an array named $Categories and populates the array with two products.

The third command creates an array named $Classification and populates the array with two update classifications.

The fourth command creates an array named $Languages and populates the array with two supported update languages, English and Brazilian Portuguese.

The last command enables the proxy setting for the update server stored in $UpdateServer.
This command sets the proxy address and port and sets the update categories, classifications, and languages to synchronize.

### Example 2: Specify a new product type setting for an update server
```
PS C:\> $UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
PS C:\> Set-SCUpdateServer -UpdateServer $UpdateServer -UpdateClassifications "Service Packs"
```

The first command gets the update server named WSUSComputer01, and then stores the object in the $UpdateServer variable.

The second command enables the service packs update classification for the update server stored in $UpdateServer.

## PARAMETERS

### -AllowConfigurationChanges
Indicates whether configuration changes to the update server are allowed.

```yaml
Type: Boolean
Parameter Sets: ConfigSettingsChange
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableProxy
Indicates that this cmdlet disables the update server from using a proxy server when it synchronizes updates.

```yaml
Type: SwitchParameter
Parameter Sets: DisableProxy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableProxy
Indicates that this cmdlet enables the update server to use a proxy server when it synchronizes updates.

```yaml
Type: SwitchParameter
Parameter Sets: EnableProxy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsProxyAccessAnonymous
Indicates whether the update server requires a proxy server to connect to the Internet.

```yaml
Type: Boolean
Parameter Sets: EnableProxy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -ProxyCredential
Specifies a credential object that contains the user name and password of an account that has permission to communicate with the proxy server.

```yaml
Type: PSCredential
Parameter Sets: Default, EnableProxy
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServerName
Specifies the name of the proxy server that the update server uses to connect with the Microsoft Update Catalog on the Internet.
You cannot use special characters, such as a forward slash (/), in this parameter.

```yaml
Type: String
Parameter Sets: EnableProxy
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProxyServerPort
Specifies the port that the update server uses to communicate with the specified proxy server.

```yaml
Type: UInt32
Parameter Sets: EnableProxy
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

### -UpdateCategories
Specifies one or more products that the update server synchronizes.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Default, ManualSync, DisableProxy, EnableProxy
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateClassifications
Specifies one or more update classifications that the update server synchronizes.
Valid values are: 

- Applications 
- Critical Updates 
- Definition Updates 
- Drivers 
- Feature Packs 
- Security Updates 
- Service Packs 
- Tools 
- Update Rollups 
- Updates

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Default, ManualSync, DisableProxy, EnableProxy
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateLanguages
Specifies one or more supported update languages that the update server synchronizes.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: Default, ManualSync, DisableProxy, EnableProxy
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer
Specifies a VMM update server object that this cmdlet modifies.

```yaml
Type: UpdateServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server for which this cmdlet configures WSUS settings.

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

### UpdateServer
This cmdlet returns an **UpdateServer** object.

## NOTES

## RELATED LINKS

[Add-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUpdateServer.md)

[Get-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md)

[Remove-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md)

