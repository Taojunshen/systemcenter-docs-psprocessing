---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225399
schema: 2.0.0
ms.assetid: A67FFBFD-EF53-4603-BD4B-A1CD48AF31B8
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClass.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClass.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClass.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMClass

## SYNOPSIS
Gets a class.

## SYNTAX

### Empty (Default)
```
Get-SCSMClass [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromClassDisplayName
```
Get-SCSMClass [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassGuids
```
Get-SCSMClass [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromEMO
```
Get-SCSMClass [-Instance] <EnterpriseManagementObject[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCSMClass [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassName
```
Get-SCSMClass [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMClass** cmdlet retrieves a class.

## EXAMPLES

### Example 1: Get all classes that partially match a name
```
PS C:\>Get-SCSMClass -name "*user"
DisplayName           Name               ManagementPackName        Id
-----------           ----               ------------------        --
Active Directory User Microsoft.AD.User  Microsoft.Windows.Library b83b8728-287a-de85-2824-916c7999b4c2
Domain User or Group  System.Domain.User System.Library            3eb2026f-1ede-e1f0-a821-c3a2036c7b1d
User                  System.User        System.Library            027e4c04-ab33-0c00-8e3b-d6f8237dee7a

DESCRIPTION: Retrieve the class with the **DisplayName** equal to "User"

PS> get-scsmclass -DisplayName User

DisplayName Name        ManagementPackName Id
----------- ----        ------------------ --
User        System.User System.Library     027e4c04-ab33-0c00-8e3b-d6f8237dee7a
```

This command retrieves all classes that end with "user."

### Example 2: Get a class by name
```
PS C:\>Get-SCSMClass -DisplayName "User"
DisplayName Name        ManagementPackName Id
----------- ----        ------------------ --
User        System.User System.Library     027e4c04-ab33-0c00-8e3b-d6f8237dee7a
```

This command retrieves the class in which **DisplayName** equals "User."

### Example 3: Get the class for an object
```
PS C:\>Get-SCSMClass -Name "System.User" | Get-SCSMClassInstance |Select-Object -First 1 | %{$_.__enterprisemanagementobject}|Get-SCSMClass
DisplayName                    Name                           ManagementPackName             Id

-----------                    ----                           ------------------             --

Active Directory User or Group Microsoft.AD.UserBase          Microsoft.Windows.Library      783ab4dd-ccd1-6458-0817-1f2adc7dcde7

Active Directory Group         Microsoft.AD.Group             Microsoft.Windows.Library      8785d166-0637-08f5-15c0-44cec44a4d3e

Domain User or Group           System.Domain.User             System.Library                 3eb2026f-1ede-e1f0-a821-c3a2036c7b1d
```

This command determines the class of an object, for which all you have is the object itself.

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
Default value: Localhost
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

### -DisplayName
Specifies the display name of the class to retrieve.

```yaml
Type: String[]
Parameter Sets: FromClassDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the class to retrieve.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromClassGuids
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of a class to retrieve.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromEMO
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies one or more management packs containing the classes to retrieve.

You can enter a **ManagementPack** object that is returned by the **Get-SCManagementPack** cmdlet.

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
Specifies the name of a class to retrieve.

```yaml
Type: String[]
Parameter Sets: FromClassName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the **Get-SCManagementGroupConnection** cmdlet.

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

### Microsoft.EnterpriseManagement.Common.EnterpriseManagementObject
You can pipe an instance of a management pack to the *Instance* parameter of the **Get-SCSMClass** cmdlet.
The **Microsoft.EnterpriseManagement.Common.EnterpriseManagementObject** object is one the properties of the **output** object of the **Get-SCSMClassinstance** cmdlet.

### System.Guid
You can pipe a GUID to the *Id* parameter of the **Get-SCSMClass** cmdlets.

### Microsoft.EnterpriseManagement.Configuration.ManagementPackManagementPack
You can pipe a management pack to the *ManagementPack* parameter of the **Get-SCSMClass** cmdlet.
This management pack object should contain the class to retrieve.

### System.String
You can pipe a name to the *Name* parameter of the **Get-SCSMClass** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
This cmdlet generates a management pack object.

## NOTES

## RELATED LINKS

[Service Manager Administrator Cmdlets Group 1](xref:SystemCenter2016/ServiceManagerCore/vlatest/ServiceManagerCore.md)

