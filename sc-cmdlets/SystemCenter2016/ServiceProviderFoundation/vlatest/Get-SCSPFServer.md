---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 65A8B565-0D2F-4984-9A1E-EAA73B1E7528
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfServer

## SYNOPSIS
Gets a server object.

## SYNTAX

### Empty (Default)
```
Get-SCSpfServer [-ServerType <String>] [<CommonParameters>]
```

### FromServerIdParameterSetName
```
Get-SCSpfServer -ID <Guid[]> [<CommonParameters>]
```

### FromServerNameParameterSetName
```
Get-SCSpfServer -Name <String[]> [<CommonParameters>]
```

### FromServerStampParameterSetName
```
Get-SCSpfServer -Stamp <Stamp> [-ServerType <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFServer** cmdlet gets one or more  VMM server objects from the Service Provider Foundation service.

To create a server, use the New-SCSPFServer cmdlet.

## EXAMPLES

### Example 1: Get all server objects
```
PS C:\>Get-SCSPFServer
```

This command gets all defined servers.

### Example 2: Get a server object by its ID
```
PS C:\>$Server = Get-SCSPFServer -ID f50e36aa-216f-4ade-a2c0-95cf17b93ee4
```

This command gets a server by its ID.

### Example 3: Get a server object by its name
```
PS C:\>$Server = Get-SCSPFServer -Name "ContosoVM"
```

This command gets a server by its name.

### Example 4: Get the server object associated with a stamp
```
PS C:\>$Stamp = Get-SCSPFStamp -Name "ContosoStamp11"
PS C:\> $Server = Get-SCSPFServer -Stamp $Stamp
```

The first command gets a stamp.
The second command gets the server associated with the stamp.

## PARAMETERS

### -ID
Specifies one or more GUIDs for a specific object.

```yaml
Type: Guid[]
Parameter Sets: FromServerIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of one or more vmm12short servers.

```yaml
Type: String[]
Parameter Sets: FromServerNameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerType
Specifies the type of server.
You can only specify 0, which designates the vmm12short server type.

```yaml
Type: String
Parameter Sets: Empty, FromServerStampParameterSetName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Stamp
Specifies a stamp for which this cmdlet returns associated servers.
To obtain a stamp, use the Get-SCSPFStamp cmdlet.

```yaml
Type: Stamp
Parameter Sets: FromServerStampParameterSetName
Aliases: 

Required: True
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

[New-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFServer.md)

[Set-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFServer.md)

[Remove-SCSPFServer](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFServer.md)

