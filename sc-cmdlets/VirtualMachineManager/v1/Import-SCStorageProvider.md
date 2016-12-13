---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCStorageProvider.md
schema: 2.0.0
ms.assetid: AE9403AA-47CA-4078-9F83-041CA6CDEB58
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Import-SCStorageProvider.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Import-SCStorageProvider.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Import-SCStorageProvider.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Import-SCStorageProvider

## SYNOPSIS
Imports storage providers that are installed and registered on a VMM management server.

## SYNTAX

```
Import-SCStorageProvider [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Import-SCStorageProvider** cmdlet imports storage providers that are installed and registered on a VMM management server.

Windows Server 2016 offers SMP as a storage provider model for storage array automation.
SMP providers are installed locally on the same server running the VMM service.
Credentials are not needed to connect to the provider (as with SMI-S providers).
After the provider is installed, **Import-SCStorageProvider** imports those providers into Virtual Machine Manager (VMM).

## EXAMPLES

### Example 1: Import storage providers
```
PS C:\>Import-SCStorageProvider
```

This command imports all storage providers that have been installed and registered on the VMM management server.

## PARAMETERS

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

[Add-SCStorageProvider](xref:VirtualMachineManager/v1/Add-SCStorageProvider.md)

[Get-SCStorageProvider](xref:VirtualMachineManager/v1/Get-SCStorageProvider.md)

[Read-SCStorageProvider](xref:VirtualMachineManager/v1/Read-SCStorageProvider.md)

[Remove-SCStorageProvider](xref:VirtualMachineManager/v1/Remove-SCStorageProvider.md)

[Set-SCStorageProvider](xref:VirtualMachineManager/v1/Set-SCStorageProvider.md)

