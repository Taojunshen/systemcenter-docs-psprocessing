---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryShare.md
schema: 2.0.0
ms.assetid: 03E44C3B-83E4-4E3C-8626-890EEF0E8380
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCLibraryShare.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCLibraryShare.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Find-SCLibraryShare.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Find-SCLibraryShare

## SYNOPSIS
Finds all of the shares on the specified computer or library server that can be added as library shares.

## SYNTAX

### New (Default)
```
Find-SCLibraryShare [-VMMServer <ServerConnection>] -Credential <VMMCredential> [-ComputerName] <String>
 [<CommonParameters>]
```

### Existing
```
Find-SCLibraryShare [-VMMServer <ServerConnection>] -LibraryServer <LibraryServer> [<CommonParameters>]
```

## DESCRIPTION
The **Find-SCLibraryShare** cmdlet finds all of the shares on the specified computer or library server that can be added as library shares.
For library servers, this command also returns shares that are already Virtual Machine Manager (VMM) library shares.

## EXAMPLES

### Example 1: Find Windows shares on a computer that is not yet a VMM library server
```
PS C:\>$Credential = Get-Credential
PS C:\> Find-SCLibraryShare -Credential $Credential -ComputerName "Server01.Contoso.com"
```

The first command uses Get-Credential to prompt you to supply a user name and password with permissions to access Windows shares on Server01 and stores your credentials in the $Credential variable.

The second command confirms that you have valid credentials for this operation and then displays all existing Windows shares capable of becoming VMM library shares.

### Example 2: Find shares on a VMM library server
```
PS C:\>Find-SCLibraryShare -LibraryServer "LibraryServer01.Contoso.com"
```

This command displays all Windows shares capable of becoming library shares that exist on LibraryServer01 as well as all shares that are already VMM library shares.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: New
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of Restart-SCJob, has permission to complete a restarted task. 



For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: New
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: Existing
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DiscoveredShare[]
This cmdlet returns an array of **DiscoveredShare** objects.

## NOTES

## RELATED LINKS

[Add-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCLibraryShare.md)

[Get-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCLibraryShare.md)

[Read-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/v1/Read-SCLibraryShare.md)

[Remove-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCLibraryShare.md)

[Set-SCLibraryShare](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCLibraryShare.md)

