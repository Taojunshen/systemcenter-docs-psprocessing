---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A6C9377D-B8EA-4C08-8EDF-E1DE889DEE1C
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOpsMgrConnection

## SYNOPSIS
Updates the Operations Manager connection settings.

## SYNTAX

```
Set-SCOpsMgrConnection [-VMMServer <ServerConnection>] [-EnableOpsMgrConnection <Boolean>]
 [-EnablePRO <Boolean>] [-EnableMaintenanceModeIntegration <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOpsMgrConnection** cmdlet updates the Operations Manager connection.
Settings that you can change include whether the connection is enabled or disabled, and whether maintenance mode integration is enabled for the connection.

## EXAMPLES

### Example 1: Disable the Operations Manager connection
```
PS C:\> Set-SCOpsMgrConnection -EnableOpsMgrConnection $False
```

This command disables the Operations Manager connection by setting the EnableOpsMgrConnection to $False.

### Example 2: Enable the Operations Manager connection
```
PS C:\> Set-SCOpsMgrConnection -EnableOpsMgrConnection $True
```

This command enables the Operations Manager connection by setting the EnableOpsMgrConnection variable to $True.

## PARAMETERS

### -EnableMaintenanceModeIntegration
Indicates whether maintenance mode integration is enabled for this connection.

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

### -EnableOpsMgrConnection
Indicates whether the connection to the Operations Manager management server is enabled.

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

### -EnablePRO
Indicates whether PRO is enabled for this connection.

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

[Get-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md)

[New-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md)

[Remove-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md)

[Write-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Write-SCOpsMgrConnection.md)

