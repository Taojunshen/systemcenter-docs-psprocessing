---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D8A45A89-7355-4197-A571-D6AA18C12D00
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMHostGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVMHostGroup

## SYNOPSIS
Changes the properties of a host group in VMM.

## SYNTAX

```
Set-SCVMHostGroup [-VMHostGroup] <HostGroup> [-Name <String>] [-Description <String>]
 [-EnableUnencryptedFileTransfer <Boolean>] [-InheritNetworkSettings <Boolean>] [-JobGroup <Guid>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMHostGroup** cmdlet changes one or more properties of a host group that contains hosts managed by Virtual Machine Manager (VMM).
Properties that you can change include settings for name, description, and whether network settings are inherited from parent host groups.

## EXAMPLES

### Example 1: Change the inherit network settings property for an existing host group
```
PS C:\> $VMHostGroup = Get-SCVMHostGroup -Name "VMHostGroup01"
PS C:\> Set-SCVMHostGroup -VMHostGroup $VMHostGroup -InheritNetworkSettings $False
```

The first command gets the host group named HostGroup01 and stores it in the $VMHostGroup variable.

The second command changes the value of the inherit network settings to false for the host group stored in $VMHostGroup.

## PARAMETERS

### -Description
Specifies a description for the host group.

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

### -EnableUnencryptedFileTransfer
Indicates, when set to $True, that network file transfers do not require encryption.
Allowing unencrypted network file transfers can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 

- Enable unencrypted file transfers into, or out of, the library. 
- Enable unencrypted file transfers into, out of, or within a host group.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AllowUnencryptedTransfers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InheritNetworkSettings
Specifies, when set to $True, that the network settings for a host group will have the same values as those specified for its parent.

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

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -Name
Specifies the name of a VMM object.

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

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
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

### HostGroup
This cmdlet returns a **HostGroup** object.

## NOTES
* Requires a VMM host group object, which can be retrieved by using the **Get-SCVMHostGroup** cmdlet.

## RELATED LINKS

[Get-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMHostGroup.md)

[Move-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Move-SCVMHostGroup.md)

[New-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMHostGroup.md)

[Remove-SCVMHostGroup](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMHostGroup.md)

