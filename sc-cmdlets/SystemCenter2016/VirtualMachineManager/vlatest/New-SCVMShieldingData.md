---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D413722F-1023-4CCE-ACE6-204E5F99BCD9
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMShieldingData.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMShieldingData.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCVMShieldingData.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMShieldingData

## SYNOPSIS
Creates a virtual machine shielding data object from a .pdk file.

## SYNTAX

### VMShieldingDataFromPath (Default)
```
New-SCVMShieldingData [-VMMServer <ServerConnection>] -VMShieldingDataPath <String> -Name <String>
 [-Description <String>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [-OnBehalfOfUser <String>] [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

### VMShieldingDataFromBytes
```
New-SCVMShieldingData [-VMMServer <ServerConnection>] -RawData <Byte[]> -Name <String> [-Description <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMShieldingData** cmdlet creates a **VMShieldingData** object from a secure provisioning blob, a .pdk file, in Virtual Machine Manager (VMM).
This file includes information such as virtual machine ownership keys, virtual machine customization information, hashes of acceptable source keys, and other information.
Tenants create a provisioning blob by using an out-of-band tool.

You can use a virtual machine shielding data object for tasks such as encrypting virtual Trusted Platform Modules (TPMs), creating shielded virtual machines, and grandfathering non-shielded virtual machines.

The VMM database manages virtual machine shielding data objects as a library resource.
They are scoped appropriately for the associated user role.
VMM provides create, read, update, and delete functionality to manage them.

## EXAMPLES

### Example 1: Create a virtual machine shielding data by using a .pdk file
```
PS C:\> New-SCVMShieldingData -Name "ShieldingData01" -Description "Shielding data" -VMShieldingDataPath "C:\virtual\SD.pdk"
```

This command creates a virtual machine shielding data object named ShieldingData01.
The command bases the object on the SD.pdk file that the *VMShieldingDataPath* parameter specifies.

### Example 2: Create a virtual machine shielding data by using raw data
```
PS C:\> $Bytes = [System.IO.File]::ReadAllBytes ("C:\virtual\SD.pdk")
PS C:\> New-SCVMShieldingData -Name "ShieldingData02" -Description "Shielding data" -RawData $Bytes
```

The first command stores the contents of SD.pdf as a byte array to the $Bytes variable.

This command creates a virtual machine shielding data object named ShieldingData02.
The command bases the object on the $Bytes array that the *RawData* parameter specifies.

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
Specifies a name for the **VMShieldingData** object.

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

### -RawData
Specifies an array of bytes that contain raw .pdk data.

```yaml
Type: Byte[]
Parameter Sets: VMShieldingDataFromBytes
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

### -VMShieldingDataPath
Specifies the path of a .pdk file.

```yaml
Type: String
Parameter Sets: VMShieldingDataFromPath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### VMShieldingData
This cmdlet returns a virtual machine shielding data object that contains the following information: 

- RawData
- KeyProtectorOwner
- KeyProtectorGuardians
- Name
- Description

## NOTES

## RELATED LINKS

[Get-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMShieldingData.md)

[Remove-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVMShieldingData.md)

[Set-SCVMShieldingData](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMShieldingData.md)

