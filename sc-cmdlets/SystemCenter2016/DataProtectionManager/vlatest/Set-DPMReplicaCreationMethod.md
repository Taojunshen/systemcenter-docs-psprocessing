---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 219DF531-95DB-4698-B06F-06687A31A1F2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMReplicaCreationMethod.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMReplicaCreationMethod.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMReplicaCreationMethod.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMReplicaCreationMethod

## SYNOPSIS
Sets the replica creation method for disk-based protection.

## SYNTAX

### Now (Default)
```
Set-DPMReplicaCreationMethod [-ProtectionGroup] <ProtectionGroup> [-Now] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### Later
```
Set-DPMReplicaCreationMethod [-ProtectionGroup] <ProtectionGroup> -Later <DateTime> [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Manual
```
Set-DPMReplicaCreationMethod [-ProtectionGroup] <ProtectionGroup> [-Manual] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMReplicaCreationMethod** cmdlet sets the replica creation method for disk-based protection.
You can set Now, Later, and Manual as the replica creation method.
If you do not specify a value, the default replica creation method is Now.

If you specify Now for disk, System Center 2016 - Data Protection Manager (DPM) starts replication as soon as you create the protection group.

The **Set-DPMReplicaCreationMethod** cmdlet is the second step in changing the replication method that you specified for a protection group.
You must first get the replica creation method by using the Get-DPMReplicaCreationMethod cmdlet.

You can use this cmdlet to set the replica creation method only if you set the protection type to short-term for disk and long-term for online.
You can use the **Set-DPMProtectionType** to set the protection type for a protection group.
If you specify any other type of protection type, this cmdlet returns an error.
This cmdlet does not apply to tape-based protection.

## EXAMPLES

### Example 1: Set the replica creation method
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "DPMServer02"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup
PS C:\> Set-DPMReplicaCreationMethod -ProtectionGroup $MPGroup -Later "23 April 2013"
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $MPGroup
```

The first command gets the protection group on the DPM server named DPMServer02, and then stores it in the $PGroup variable.

The second command makes the protection group in $PGroup modifiable, and stores the result in the $MPGroup variable.

The third command sets the replica creation method to Later for the protection group in $MPGroup to create a replica on April 23, 2013.

The fourth command uses the **Set-DPMProtectionGroup** cmdlet to save your changes.

## PARAMETERS

### -Later
Specifies the time at which DPM performs the operation.

```yaml
Type: DateTime
Parameter Sets: Later
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Manual
Indicates that you apply settings manually.

```yaml
Type: SwitchParameter
Parameter Sets: Manual
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Now
Indicates that DPM creates the replica immediately.

```yaml
Type: SwitchParameter
Parameter Sets: Now
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -ProtectionGroup
Specifies a protection group for which this cmdlet sets the replica creation method.
To obtain a **ProtectionGroup** object, use the Get-DPMProtectionGroup cmdlet.

```yaml
Type: ProtectionGroup
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

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

### ProtectionGroup

## NOTES

## RELATED LINKS

[Get-DPMProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMProtectionGroup.md)

[Get-DPMModifiableProtectionGroup](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMModifiableProtectionGroup.md)

[Get-DPMReplicaCreationMethod](xref:SystemCenter2016/DataProtectionManager/vlatest/Get-DPMReplicaCreationMethod.md)

[Set-DPMProtectionType](xref:SystemCenter2016/DataProtectionManager/vlatest/Set-DPMProtectionType.md)

