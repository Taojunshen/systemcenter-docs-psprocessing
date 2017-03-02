---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BCA0EA83-D822-4A90-ADA2-B030494BB169
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Test-SCPROTip.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
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

### Example 1: Test PRO integration between VMM and Operations Manager
```
PS C:\> $PROTipJob = Test-SCPROTip
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

[Add-PROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-PROTip.md)

[Clear-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Clear-SCPROTip.md)

[Get-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPROTip.md)

[Invoke-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Invoke-SCPROTip.md)

[Set-SCPROTip](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCPROTip.md)

