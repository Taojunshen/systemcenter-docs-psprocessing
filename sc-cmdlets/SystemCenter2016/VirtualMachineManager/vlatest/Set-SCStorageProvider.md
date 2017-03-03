---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 54D4C56B-EDF7-47BB-AD8B-32D7E7456598
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCStorageProvider

## SYNOPSIS
Modifies a storage provider object in VMM.

## SYNTAX

```
Set-SCStorageProvider [-StorageProvider] <StorageProvider> [-Name <String>] [-Description <String>]
 [-RunAsAccount <RunAsAccount>] [-NetworkDeviceName <String>] [-TCPPort <UInt32>]
 [-Certificate <ClientCertificate>] [-JobGroup <Guid>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCStorageProvider** cmdlet modifies a storage provider object in Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Change the name of a storage provider
```
PS C:\> $Provider = Get-SCStorageProvider -Name "StorProv01.Contoso.com"
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Set-SCStorageProvider -StorageProvider $Provider -NetworkDeviceName "http://StorProv01.Contoso.com" -Name "NewStorProvName.Contoso.com" -RunAsAccount $RunAsAcct
```

The first command gets the storage provider named StorProv01 and stores it in the $Provider variable.

The second command gets RunAs account RunAsAccount01 and stores it in the $RunAsAcct variable.

The last command sets the network device name of the storage provider stored in the $Provider variable to NewStorProvName using the RunAs account stored in $RunAsAcct.

### Example 2: Change the TCP/IP port of a storage provider
```
PS C:\> $Provider = Get-SCStorageProvider -Name "StorProv01.Contoso.com"
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Set-SCStorageProvider -StorageProvider $Provider -TCPPort 40441 -RunAsAccount $RunAsAcct
```

The first command gets the storage provider named StorProv01 and stores it in the $Provider variable.

The second command gets the RunAs account named RunAsAccount01 and stores the object in the $RunAsAcct variable.

The third command changes the TCP/IP port of the storage provider stored in $Provider to 40441 using the RunAs account stored in $RunAsAcct.

## PARAMETERS

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the storage provider.

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

### -JobGroup
Specifies an ID for a series of commands that run as a set just before the final command that includes the same job group ID runs.

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

### -NetworkDeviceName
Specifies the name of a network device.

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

### -StorageProvider
Specifies a storage provider object.

```yaml
Type: StorageProvider
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: UInt32
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

### StorageProvider
This cmdlet returns a **StorageProvider** object.

## NOTES

## RELATED LINKS

[Add-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCStorageProvider.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCStorageProvider.md)

[Import-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Import-SCStorageProvider.md)

[Read-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCStorageProvider.md)

[Remove-SCStorageProvider](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCStorageProvider.md)

