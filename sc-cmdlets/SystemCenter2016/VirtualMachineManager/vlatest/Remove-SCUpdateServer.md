---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 243D37FA-E041-4AA7-917E-9B1644E225A2
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCUpdateServer

## SYNOPSIS
Removes a WSUS server from VMM.

## SYNTAX

```
Remove-SCUpdateServer [-VMMServer <ServerConnection>] [-UpdateServer] <UpdateServer>
 -Credential <VMMCredential> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCUpdateServer** cmdlet removes a Microsoft Windows Server Update Services (WSUS) computer from Virtual Machine Manager (VMM).
Removing WSUS integration disables the update management feature in VMM.

## EXAMPLES

### Example 1: Remove an update server
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $UpdateServer = Get-SCUpdateServer -ComputerName "WSUSComputer01"
PS C:\> Remove-SCUpdateServer -UpdateServer $UpdateServer -Credential $Credential
```

The first command gets the Run As account named RunAsAccount01, and then stores that object in the $Credential variable.

The second command gets the update server object named WSUSComputer01, and then stores the object in the $UpdateServer variable.

The last command removes the update server stored in $UpdateServer.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object that contains the user name and password of an account that has permission to perform this action.

```yaml
Type: VMMCredential
Parameter Sets: (All)
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

### -UpdateServer
Specifies a VMM update server from which this cmdlet removes the update server.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Get-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md)

[Set-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md)

