---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-PROTip.md
schema: 2.0.0
ms.assetid: BCA0EA83-D822-4A90-ADA2-B030494BB169
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Test-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Test-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Test-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Test-SCPROTip

## SYNOPSIS
Tests PRO integration between VMM and Operations Manager.

## SYNTAX

```
Test-SCPROTip [-VMMServer <ServerConnection>] [<CommonParameters>]
```

## DESCRIPTION
The **Test-SCPROTip** cmdlet tests integration between Virtual Machine Manager (VMM) and Operations Manager.
After creating a connection with Operations Manager and configuring Performance and Resource Optimization (PRO) monitors, run **Test-SCPROTip** to validate that PRO integration is functioning correctly.
**Test-SCPROTip** creates a new warning PRO alert in Operations Manager, invokes a remediation, and then implements the fix for the PRO tip.

## EXAMPLES

### Example 1: Test PRO integration between VMM and om12short
```
PS C:\>$PROTipJob = Test-SCPROTip
PS C:\> $PROTipJob
```

The first command runs the **Test-SCPROTip** operation and stores the associated job in the variable named $PROTipJob.

The second command verifies the status of the test.
You can also view the status in the VMM job interface.

## PARAMETERS

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

[Add-PROTip](xref:VirtualMachineManager/v1/Add-PROTip.md)

[Clear-SCPROTip](xref:VirtualMachineManager/v1/Clear-SCPROTip.md)

[Get-SCPROTip](xref:VirtualMachineManager/v1/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:VirtualMachineManager/v1/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:VirtualMachineManager/v1/Set-SCPROTip.md)

