---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3001397D-08C7-49C3-829F-88EA340A9649
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCOpsMgrConnection

## SYNOPSIS
Gets the Operations Manager connection object.

## SYNTAX

```
Get-SCOpsMgrConnection [-VMMServer <ServerConnection>] [-Connect] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOpsMgrConnection** cmdlet gets the Operations Manager connection object if a connection has been created.

For information about how to create an Operations Manager connection, type `Get-Help New-SCOpsMgrConnection -Detailed`.

## EXAMPLES

### Example 1: Get the Operations Manager connection object
```
PS C:\> $OMConn = Get-SCOpsMgrConnection
PS C:\> $OMConn
```

The first command gets the Operations Manager connection object stores it in the $OMConn variable.

The second command displays the Operations Manager connection object stored in $OMConn to the user.

## PARAMETERS

### -Connect
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

### OpsMgrConnection
This cmdlet returns an **OpsMgrConnection** object.

## NOTES

## RELATED LINKS

[New-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md)

[Remove-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md)

[Set-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md)

[Write-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Write-SCOpsMgrConnection.md)

