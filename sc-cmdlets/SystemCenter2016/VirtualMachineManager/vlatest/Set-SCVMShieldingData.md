---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 6A178D9A-32B8-405A-8121-48749DBB2435
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMShieldingData.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMShieldingData.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMShieldingData.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCVMShieldingData

## SYNOPSIS
Modifies a VMShieldingData object.

## SYNTAX

```
Set-SCVMShieldingData [-VMShieldingData] <KeyFile> [-VMMServer <ServerConnection>] [-Description <String>]
 [-Name <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVMShieldingData** cmdlet modifies a **VMShieldingData** object in Virtual Machine Manager (VMM).
The properties you can modify are Name and Description.

## EXAMPLES

### Example 1: Set the name of a shielding data object
```
PS C:\> $TestVMShieldingData = New-SCVMShieldingData -Name "ShieldingData01" -Description "Test" -VMShieldingDataPath "C:\virtual\SD.pdk"
PS C:\> Set-SCVMShieldingData -VMShieldingData $TestVMShieldingData -Name "NewShieldingData01"
```

The first command creates a shielding data object named ShieldingData01, and then stores it in the $TestVMShieldingData variable.

The second command sets the name of the object in $TestVMShieldingData to NewShieldingData01.

## PARAMETERS

### -Description
Specifies a description for the **VMShieldingData** object.

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

### -JobVariable
Specifies the name of a variable in which job progress is tracked and stored.

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
Specifies the name of the **VMShieldingData** object.

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

### -OnBehalfOfUser
Specifies a user name.
This cmdlet operates on behalf of the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
To obtain a user role, use the **Get-SCUserRole** cmdlet.
This cmdlet operates on behalf of the user role that this parameter specifies.

```yaml
Type: UserRole
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

### -VMShieldingData
Specifies the **VMShieldingData** object to modify.

```yaml
Type: KeyFile
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

### VMShieldingData
This cmdlet returns the updated **VMShieldingData** object.

## NOTES

## RELATED LINKS

[Get-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMShieldingData.md)

[New-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMShieldingData.md)

[Remove-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMShieldingData.md)

