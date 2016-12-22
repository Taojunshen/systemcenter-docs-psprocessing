---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: AAEED357-90DC-46B3-ACF1-7D962646EFA1
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCSQLProfile

## SYNOPSIS
Modifies the properties of a SQL Server profile.

## SYNTAX

```
Set-SCSQLProfile [-VMMServer <ServerConnection>] [-SQLProfile] <SQLProfile> [-Name <String>]
 [-Description <String>] [-Owner <String>] [-UserRole <UserRole>] [-Tag <String>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSQLProfile** cmdlet modifies the properties of a Microsoft SQL Server profile.

## EXAMPLES

### Example 1: Change the name and description of a SQL Server profile
```
PS C:\> $SQLProfile = Get-SCSQLProfile -Name "SQLProfile01"
PS C:\> Set-SCSQLProfile -SQLProfile $SQLProfile -Name "SQLProfile02" -Description "SQL Profile 02"
```

The first command gets the SQL Server profile named SQLProfile01, and then stores that object in the $SQLProfile variable.

The second command renames the SQL Server profile stored in $SQLProfile and changes its description.

## PARAMETERS

### -Description
Specifies a description that this cmdlet modifies for the SQL Server profile.

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
Specifies a variable in which job progress is tracked and stored.

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
Specifies the new name of the SQL Server profile.

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

### -Owner
Specifies the owner of a SQL Server profile.
Specify a valid domain user account in the following formats: 

- `Contoso\DavidCh` 
- `DavidCh@Contoso`

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
Specifies the ID of the Performance and Resource Optimization (PRO) tip that triggered this action.
This allows for auditing of PRO tips.

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

### -SQLProfile
Specifies the SQL Server profile that this cmdlet modifies.

```yaml
Type: SQLProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tag
Specifies a word or phrase that this cmdlet associates to an object.
You can search for a subset of tags, or you can search for the full set of tags.

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

### -UserRole
Specifies the user role for the SQL Server profile.

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

### -VMMServer
Specifies the VMM server on which this cmdlet operates.

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

### SQLProfile
This cmdlet returns a **SQLProfile** object.

## NOTES

## RELATED LINKS

[Get-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLProfile.md)

[New-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/New-SCSQLProfile.md)

[Remove-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLProfile.md)

