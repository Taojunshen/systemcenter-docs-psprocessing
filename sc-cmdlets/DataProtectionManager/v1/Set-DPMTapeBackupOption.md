---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Get-DPMProtectionGroup.md
schema: 2.0.0
ms.assetid: 6319877F-D22E-42BC-96BE-80065DD9E267
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMTapeBackupOption.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMTapeBackupOption.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/DataProtectionManager/v1/Set-DPMTapeBackupOption.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-DPMTapeBackupOption

## SYNOPSIS
Modifies the tape backup and library options for a DPM protection group.

## SYNTAX

### ShortTerm
```
Set-DPMTapeBackupOption [-ProtectionGroup] <ProtectionGroup> [-ShortTerm] [-CompressData] [-EncryptData]
 [-PerformIntegritycheck] [-PassThru] [-RemovePGSet] [-PGSet <PGSet>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LongTerm
```
Set-DPMTapeBackupOption [-ProtectionGroup] <ProtectionGroup> [-LongTerm] [-CompressData] [-EncryptData]
 [-PerformIntegritycheck] [-PassThru] [-RemovePGSet] [-PGSet <PGSet>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### LibraryOptions
```
Set-DPMTapeBackupOption [-ProtectionGroup] <ProtectionGroup> -BackupLibrary <Library>
 [-TapeCopyLibrary <Library>] -DrivesAllocated <Int32> [-PassThru] [-RemovePGSet] [-PGSet <PGSet>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMTapeBackupOption** cmdlet modifies the tape backup options for a System Center 2016 - Data Protection Manager (DPM) protection group.
These options include library and drive information, and short-term and long-term tape backup options.

## EXAMPLES

### Example 1: Set tape backup options for short-term backup
```
PS C:\>$PGroup = Get-DPMProtectionGroup -DPMServerName "Contoso-DPMServer"
PS C:\> Set-DPMTapeBackupOption -ProtectionGroup $PGroup -ShortTerm -EncryptData
```

The first command uses the **Get-ProtectionGroup** cmdlet to get a protection group for Contoso-DPMServer.
The command stores the group in the $PGroup variable.

The second command specifies values for the *ShortTerm* and *Encryption* parameters.
This example sets the tape backup options to short-term backup with encryption.

### Example 2: Set tape backup options for a protection group
```
PS C:\>$PGroup = Get-DPMProtectionGroup "Contoso-DPMServer"
PS C:\> $MPGroup = Get-DPMModifiableProtectionGroup -ProtectionGroup $PGroup[0]
PS C:\> $DpmLibrary = Get-DPMLibrary "Contoso-DPMServer"
PS C:\> Set-DPMTapeBackupOption -ProtectionGroup $MPGroup -BackupLibrary $DpmLibrary -DrivesAllocated 1
PS C:\> Set-DPMProtectionGroup -ProtectionGroup $MPGroup
```

The first command uses the **Get-ProtectionGroup** cmdlet to get a protection group for Contoso-DPMServer.
The command stores the group in the $PGroup variable.

The second command uses the **Get-ModifiableProtectionGroup** cmdlet to retrieve the settings for the first protection group.
The command stores the group in editable mode in the $MPGroup variable.

The third command uses the **Get-DPMLibrary** cmdlet to get the library for Contoso-DMPServer.
The command stores it in the $DpmLibrary variable.

The fourth command specifies values for the *BackupLibrary* and *DrivesAllocated* parameters.
This example sets the tape backup option for the protection group.

The fifth command uses the **Set-ProtectionGroup** cmdlet to save your changes to the value in $MPGroup.

## PARAMETERS

### -BackupLibrary
Specifies a backup library.

```yaml
Type: Library
Parameter Sets: LibraryOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CompressData
Indicates that the backup process compresses the data to reduce storage needs.
Do not use compression and encryption together.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTerm, LongTerm
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DrivesAllocated
Specifies the number of drives to allocate to the protection group.

```yaml
Type: Int32
Parameter Sets: LibraryOptions
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptData
Indicates that the backup process encrypts the data during backup.
Do not use compression and encryption together.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTerm, LongTerm
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LongTerm
Indicates that the protection group uses long-term tape protection.
Do not use this parameter with the **ShortTerm** parameter.
You must set *LongTerm* and *ShortTerm* options in separate commands.

```yaml
Type: SwitchParameter
Parameter Sets: LongTerm
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

### -PerformIntegritycheck
Indicates that the backup process performs an integrity check on the tape backup.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTerm, LongTerm
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PGSet
Specifies the protection group set for which this cmdlet modifies options.
To obtain a protection group set object, use the Get-DPMPGSet cmdlet.

```yaml
Type: PGSet
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtectionGroup
Specifies a protection group for which this cmdlet modifies options.
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

### -RemovePGSet
Indicates that the cmdlet removes the protection group set as an option.

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

### -ShortTerm
Indicates that the protection group will be on disk, on tape, or on neither, if nothing is specified.
Do not use this parameter with the *LongTerm* parameter.
You must set *LongTerm* and *ShortTerm* options in separate commands.

```yaml
Type: SwitchParameter
Parameter Sets: ShortTerm
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TapeCopyLibrary
Specifies a library object.
Use the secondary tape library to make copies of the tape in the backup library.

```yaml
Type: Library
Parameter Sets: LibraryOptions
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

[Get-DPMProtectionGroup](xref:DataProtectionManager/v1/Get-DPMProtectionGroup.md)

[Get-DPMModifiableProtectionGroup](xref:DataProtectionManager/v1/Get-DPMModifiableProtectionGroup.md)

[Get-DPMLibrary](xref:DataProtectionManager/v1/Get-DPMLibrary.md)

[Get-DPMTapeBackupOption](xref:DataProtectionManager/v1/Get-DPMTapeBackupOption.md)

[Set-DPMProtectionGroup](xref:DataProtectionManager/v1/Set-DPMProtectionGroup.md)

