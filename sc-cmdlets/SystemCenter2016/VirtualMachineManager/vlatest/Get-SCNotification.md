---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D11E3DC6-8B1C-418A-A0A8-A372CEEDD5A6
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNotification.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNotification.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCNotification.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCNotification

## SYNOPSIS
Gets update notifications for a service template or service instance.

## SYNTAX

```
Get-SCNotification [-VMMServer <ServerConnection>] [-NotifiedObject] <ClientObject> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCNotification** cmdlet gets the update notifications for a service template or service instance.
Update notifications alert you to updated resources that are available for a service template or service instance.
Use the **Set-SCNotification** cmdlet to dismiss notifications.

## EXAMPLES

### Example 1: Get update notifications for a service
```
PS C:\> $Service = Get-SCService -Name "Service01"
PS C:\> Get-SCNotification -NotifiedObject $Service
```

The first command gets the service object named Service01 and stores the object in the $Service variable.

The second command gets all update notifications for Service01.

## PARAMETERS

### -NotifiedObject
Specifies a service template object or service instance object for which you want to retrieve update notifications.

```yaml
Type: ClientObject
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies a Virtual Machine Manager (VMM) server object.

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

[Get-SCService](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCService.md)

[Set-SCNotification](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCNotification.md)

