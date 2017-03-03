---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BDB65E72-4B55-451E-B270-5204A085188B
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMUser.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMUser.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMUser.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMUser

## SYNOPSIS
Retrieves users that are defined in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMUser [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMUser [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromName
```
Get-SCSMUser [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMUser** cmdlet retrieves users that are defined in Service Manager.
Depending on the configuration of the system, the users can be a collection of Windows Active Directory users, and users that are defined in other operating systems, such as UNIX.

## EXAMPLES

### Example 1: Get available User objects in Service Manager
```
PS C:\>Get-SCSMUser
The properties displayed are FirstName, LastName, Domain, and UserName
FirstName   LastName    Domain      UserName
----------  ---------   -------     ---------
David       Chew        SMInternal  David.Chew
```

This command retrieves **User** objects that are available in Service Manager.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

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
Specifies the display name of the user to retrieve.
You can specify a regular expression.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the user to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the user to retrieve.
You can specify a regular expression

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

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

### System.String
You can pipe a name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### Microsoft.AD.User
This cmdlet returns a **User** object that provides the information about the Service Manager **User**.
This object can be used in conjunction with the Update-SCSMUserRole cmdlet to add a user to a user role.

### Microsoft.AD.Group

### System.Domain.User

## NOTES

## RELATED LINKS

[Update-SCSMUserRole](xref:SystemCenter2016/ServiceManager/vlatest/Update-SCSMUserRole.md)

