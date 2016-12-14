---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=191955
schema: 2.0.0
ms.assetid: E57C71B4-324B-4CBB-91EA-ED6A71D1E850
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMRunAsProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMRunAsProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMRunAsProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMRunAsProfile

## SYNOPSIS
Gets Run As profiles.

## SYNTAX

### Empty (Default)
```
Get-SCOMRunAsProfile [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRunAsProfileDisplayName
```
Get-SCOMRunAsProfile [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCOMRunAsProfile -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCOMRunAsProfile [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRunAsProfileName
```
Get-SCOMRunAsProfile -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMRunAsProfile** cmdlet gets Run As profiles.
A Run As profile is a group of associated Run As accounts that manages credentials and their distribution to different computers.

## EXAMPLES

### Example 1: Get Run As profiles by using a name
```
PS C:\>Get-SCOMRunAsProfile -Name "Microsoft.SystemCenter*"
```

This command gets the Run As profiles that have names that begin with Microsoft.SystemCenter.

### Example 2: Get a Run As profile by using a display name
```
PS C:\>Get-SCOMRunAsProfile -DisplayName "Automatic Agent Management Account"
```

This command gets the Run As profile that has the display name Automatic Agent Management Account.

### Example 3: Get a Run As profile by using an ID
```
PS C:\>Get-SCOMRunAsProfile -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the Run As profile that has the Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

### Example 4: Get all Run As profiles for a management pack
```
PS C:\>Get-SCOMManagementPack -DisplayName "System Center Core Library" | Get-SCOMRunAsProfile
```

This command gets the management pack named System Center Core Library and uses the pipeline operator to pass that management pack object to the **Get-SCOMRunAsProfile** cmdlet.
The cmdlet gets all Run As profiles for the management pack.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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
Specifies a user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, or a user name such as User01, Domain01\User01, or User@Domain.com.
If you type a user name, the cmdlet prompts you for a password.
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

### -DisplayName
Specifies an array of display names for Run As profiles.
The cmdlet takes each string in the array and looks for matches among the display names of the Run As profiles that this cmdlet works with.
Values for this parameter vary depending on which localized management packs are imported into the management group and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromRunAsProfileDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
Specifies an array of IDs of Run As profiles.
The cmdlet gets Run As profiles that have these IDs.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies an array of management pack objects.
The cmdlet gets the Run As profiles for the management pack objects in the array.
To obtain management pack objects, use the **Get-SCOMManagementPack** cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of Run As profiles.
The cmdlet takes each string in the array and looks for matches among the names of the Run As profiles that this cmdlet works with.

```yaml
Type: String[]
Parameter Sets: FromRunAsProfileName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.MonitoringSecureReference

## NOTES

## RELATED LINKS

[Add-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/v1.0/Add-SCOMRunAsProfile.md)

[Get-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMRunAsProfile.md)

[Remove-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/v1.0/Remove-SCOMRunAsProfile.md)

[Set-SCOMRunAsProfile](xref:SystemCenter2016/OperationsManager/v1.0/Set-SCOMRunAsProfile.md)

