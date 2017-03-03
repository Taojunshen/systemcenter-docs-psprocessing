---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 49487932-9B10-4A9E-B10B-1F2AF91B714F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMRunAsProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMRunAsProfile

## SYNOPSIS
Adds a Run As profile.

## SYNTAX

```
Add-SCOMRunAsProfile -ManagementPack <ManagementPack[]> [-Name] <String> [[-DisplayName] <String>]
 [[-Description] <String>] [[-Comment] <String>] [[-Guid] <Guid>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMRunAsProfile** cmdlet adds a Run As profile.
A Run As profile is a group of associated Run As accounts that help manage credentials and their distribution to different computers.

## EXAMPLES

### Example 1: Add a Run As profile to a management pack
```
PS C:\>$Mp = Get-SCOMManagementPack -Name "*DefaultUser"
PS C:\> Add-SCOMRunAsProfile -Name "Contoso.MonitoringProfile" -ManagementPack $Mp
```

This example adds a Run As profile to a management pack.

The first command gets the management packs that have names that end with DefaultUser and stores those management packs in the variable named $Mp.

The second command creates the Run As profile named Contoso.MonitoringProfile and adds the management packs stored in $Mp to it.

## PARAMETERS

### -Comment
Specifies an administrative comment for the profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, specify the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -Credential
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about credential objects, type "`Get-Help Get-Credential`".

This account must have access to the server that the *ComputerName* parameter specifies, if that parameter appears.

If you do not specify this parameter, the default is the account for the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description of the Run As profile.
If this parameter is not specified, the default description is the description specified in the *DisplayName* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the Run As profile.
If this parameter is not specified, the default display name is the name specified in the *Name* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid
Specifies a globally unique identifier (GUID) to identify the Run As profile.
If this parameter is not specified, the cmdlet generates a new GUID.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagementPack
Specifies an array of **ManagementPack** objects.
The cmdlet saves the RunAs profile in these management packs.
To obtain a **ManagementPack** object, use the **Get-SCOMManagementPack** cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the Run As profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter does not appear, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type "`Get-Help about_OpsMgr_Connections`".

```yaml
Type: Connection[]
Parameter Sets: (All)
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

## NOTES

## RELATED LINKS

[Get-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsProfile.md)

[Remove-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMRunAsProfile.md)

[Set-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMRunAsProfile.md)

