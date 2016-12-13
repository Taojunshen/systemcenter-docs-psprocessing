---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239491
schema: 2.0.0
ms.assetid: EFA594B1-39B9-44DF-A877-ABC88864C775
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMRunAsProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMRunAsProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Remove-SCOMRunAsProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCOMRunAsProfile

## SYNOPSIS
Removes a Run As profile from a management group.

## SYNTAX

```
Remove-SCOMRunAsProfile [-RunAsProfile] <ManagementPackSecureReference[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCOMRunAsProfile** cmdlet removes a Run As profile from a management group.
A Run As profile is a group of associated Run As accounts that manage credentials and their distribution to different computers.

## EXAMPLES

### Example 1: Remove a Run As profile
```
PS C:\>Get-SCOMRunAsProfile "Profile01" | Remove-SCOMRunAsProfile
```

This command removes the Profile01 profile.
The command uses the **Get-SCOMRunAsProfile** cmdlet to get the specified profile and passes it to the **Remove-SCOMRunAsProfile** cmdlet by using the pipeline operator.

## PARAMETERS

### -ComputerName
Specifies an array that contains the name of the computer with which to establish a connection.
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

This account must have access to the server that is specified in the *ComputerName* parameter if that parameter appears.

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

### -RunAsProfile
Specifies an array that contains the Run As profile to remove.

```yaml
Type: ManagementPackSecureReference[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

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

[Add-SCOMRunAsProfile](xref:OperationsManager/v1/Add-SCOMRunAsProfile.md)

[Get-SCOMRunAsProfile](xref:OperationsManager/v1/Get-SCOMRunAsProfile.md)

[Set-SCOMRunAsProfile](xref:OperationsManager/v1/Set-SCOMRunAsProfile.md)

