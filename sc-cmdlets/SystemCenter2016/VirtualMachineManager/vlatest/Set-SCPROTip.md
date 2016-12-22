---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 523B6B08-49FF-444F-97C5-29D13924F471
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPROTip

## SYNOPSIS
Sets the status of a PRO tip.

## SYNTAX

```
Set-SCPROTip [-VMMServer <ServerConnection>] -PROTipID <String> [-TipStatus <String>] [-ActionSummary <String>]
 [-ActionDetails <String>] [-ActionScript <String>] [-ActionDetailsOpsMgrString <String[]>]
 [-ActionSummaryOpsMgrString <String[]>] [-LastErrorOpsMgrString <String[]>] [-LastError <String>]
 [-RunAsynchronously] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPROTip** cmdlet sets the status of a Performance and Resource Optimization (PRO) tip object.
This cmdlet, which is called by PRO tip implementation actions and is for use in building PRO Packs, is used by Virtual Machine Manager (VMM) to update the status of a PRO tip while performing the action recommended by the PRO tip.
You can use this cmdlet to manually update the status of PRO tips.

## EXAMPLES

### Example 1: Set the status of a PRO tip
```
PS C:\> $PROTips = Get-SCPROTip
PS C:\> Set-SCPROTip -PROTipID $PROTips[0].Id -TipStatus Running
```

The first command gets all active PRO tip objects from the VMM database and stores the objects in the $AllPROTips object array.

The last command updates the first tip stored in $PROTips (as designated by the \[0\]) to the status Running.

## PARAMETERS

### -ActionDetails
Provides a detailed description of what implementing this PRO tip will do.

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

### -ActionDetailsOpsMgrString
Specifies an array of strings used to provide translated action details text.
The first element of the array should be the GUID of the Operations Manager string and the following elements should be the parameters for string formatting.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ActionScript
Specifies the script that will run by implementing this PRO tip.

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

### -ActionSummary
Provides a summary description of what implementing this PRO tip will do.

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

### -ActionSummaryOpsMgrString
Specifies an array of strings used to provide translated action summary text.
The first element of the array should be the GUID of the Operations Manager string and the following elements should be the parameters for string formatting.

```yaml
Type: String[]
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

### -LastError
Specifies the error text of a runtime error from a PRO tip script.

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

### -LastErrorOpsMgrString
Specifies an array of strings used to provide translated error text.
The first element of the array should be the GUID of the Operations Manager string and the following elements should be the parameters for string formatting.

```yaml
Type: String[]
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
Type: String
Parameter Sets: (All)
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

### -TipStatus
Specifies the current status of a PRO tip object.
The acceptable values for this parameter are:

- Active.
The user can invoke the tip's recommended action.
- Initialized.
The tip has been invoked; any incomplete jobs are queued.
- Auto.
- Running.
The tip has been invoked; its jobs are running.
- Resolved.
The implementation of the tip has completed successfully.
- Failed.
The implementation of the tip has failed.
- Dismissed.
The user has chosen to ignore the tip.
- Closed.

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

### PROTip
This cmdlet returns a **PROTip** object.

## NOTES

## RELATED LINKS

[Add-PROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md)

[Clear-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md)

[Get-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md)

[Test-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md)

