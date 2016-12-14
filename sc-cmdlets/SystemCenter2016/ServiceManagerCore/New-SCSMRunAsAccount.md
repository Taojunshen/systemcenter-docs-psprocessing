---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225408
schema: 2.0.0
ms.assetid: FC3056F1-D483-4E37-A7A1-DAD69266068A
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/New-SCSMRunAsAccount.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/New-SCSMRunAsAccount.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/New-SCSMRunAsAccount.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSMRunAsAccount

## SYNOPSIS
Creates a RunAs account.

## SYNTAX

```
New-SCSMRunAsAccount [-PassThru] [-ManagementPack] <ManagementPack> -Password <SecureString> -UserName <String>
 -Domain <String> -DisplayName <String> [-Description <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMRunAsAccount** cmdlet creates a RunAs account.

## EXAMPLES

### Example 1: Create a RunAs account
```
PS C:\>$Arguments = @{
>> ManagementPack = Get-SCManagementPack -DisplayName Default*
>> Password = Read-Host â€"AsSecureString "Password" 
>> UserName = "Administrator"
>> Domain = "CONTOSO"
>> DisplayName = "Patti Fuller"
>> Description = "Patti Fuller"
>> }
PS C:\>New-SCSMRunAsAccount @Arguments
PS C:\>Get-SCRunAsAccount -DisplayName "Patti Fuller"
```

This command in this example creates a RunAs account.

## PARAMETERS

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

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
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.

The default value is the current user.
You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies the description of the RunAs account.

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

### -DisplayName
Specifies the display name of the RunAs account.

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

### -Domain
Specifies the domain of the user for the RunAs account.

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

### -ManagementPack
Specifies the management pack in which the RunAs account will be stored.
You can provide a **ManagementPack** object that is returned by the Get-SCSMManagementPack cmdlet.

```yaml
Type: ManagementPack
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Specifies the output object that represents the RunAs account.
This output object can be passed to other cmdlets.

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

### -Password
Specifies the password to be used with the RunAs account.
Use **Read-Host -assecurestring** to provide the password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the Get-SCSMManagementGroupConnection cmdlet.

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

### -UserName
Specifies the user name to associate with the RunAs account.

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

###  
You cannot pipe input to this cmdlet.

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMRunAsAccount.md)

[Remove-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/Remove-SCSMRunAsAccount.md)

[Update-SCSMRunAsAccount](xref:SystemCenter2016/ServiceManagerCore/Update-SCSMRunAsAccount.md)

[Get-SCSMManagementGroupConnection](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMManagementGroupConnection.md)

[Get-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/Get-SCSMManagementPack.md)

