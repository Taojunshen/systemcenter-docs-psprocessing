---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVirtualizationManager.md
schema: 2.0.0
ms.assetid: 0AE5EC67-0FE0-4023-990B-97911EE170E1
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualizationManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualizationManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCVirtualizationManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCVirtualizationManager

## SYNOPSIS
Refreshes the properties of a VMware vCenter Server so that the VMM console displays updated information about vCenter Server entities.

## SYNTAX

```
Read-SCVirtualizationManager [-VirtualizationManager] <VirtualizationManager> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCVirtualizationManager** cmdlet refreshes the properties of a VMware vCenter Server managed by Virtual Machine Manager (VMM) so that the VMM console displays updated information about vCenter Server entities.

## EXAMPLES

### Example 1: Refresh all VMware vCenter Servers managed by VMM
```
PS C:\>$VirtManagers = Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com"
PS C:\> ForEach ($VManager in $VirtManagers) {Read-SCVirtualizationManager -VirtualizationManager $VManager}
```

The first command retrieves all virtualizaton manager objects from the VMM database on VMMServer01 and stores the returned objects in the $VirtManagers array.

The second command uses a **ForEach** loop statement to refresh the properties of the objects stored in $VirtManagers so that current information about these virtualization managers displays in the VMM console.

For more information about the standard Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

### Example 2: Refresh a specific VMware vCenter Server managed by VMM
```
PS C:\>$VirtManager = Get-SCVirtualizationManager -VMMServer "VMMServer01.Contoso.com" -ComputerName "VirtMgrServer01.Contoso.com"
PS C:\> Read-SCVirtualizationManager -VirtualizationManager $VirtManager
```

The first command gets the virtualizaton manager object named VirtMgrServer01 from VMMServer01 and stores the object in $VirtManager.

The second command refreshes the properties for the object stored in $VirtManager so that current information about this virtualization manager displays in the VMM console.

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

### -VirtualizationManager
Specifies a virtualization manager object managed by VMM.

```yaml
Type: VirtualizationManager
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualizationManager
This cmdlet returns a **VirtualizationManager** object.

## NOTES
* Requires a VMM virtualization manager object, which can be retrieved by using the Get-SCVirtualizationManager cmdlet.

## RELATED LINKS

[Add-SCVirtualizationManager](xref:VirtualMachineManager/v1/Add-SCVirtualizationManager.md)

[Get-SCVirtualizationManager](xref:VirtualMachineManager/v1/Get-SCVirtualizationManager.md)

[Remove-SCVirtualizationManager](xref:VirtualMachineManager/v1/Remove-SCVirtualizationManager.md)

[Set-SCVirtualizationManager](xref:VirtualMachineManager/v1/Set-SCVirtualizationManager.md)
