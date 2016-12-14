---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=187691
schema: 2.0.0
ms.assetid: 7123A5D8-F693-4B5F-AC54-8D118006202A
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMClassInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMClassInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1.0/Get-SCOMClassInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMClassInstance

## SYNOPSIS
Gets class instances.

## SYNTAX

### Empty (Default)
```
Get-SCOMClassInstance [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCOMClassInstance [-Class] <ManagementPackClass[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMODisplayNameParameterSetName
```
Get-SCOMClassInstance [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMONameParameterSetName
```
Get-SCOMClassInstance -Name <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromGroup
```
Get-SCOMClassInstance [-Group] <EnterpriseManagementObject[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMOIdParameterSetName
```
Get-SCOMClassInstance -Id <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMClassInstance** cmdlet gets one or more class instances.
A class represents a kind of object, and every object in System Center 2016 - Operations Manager is considered an instance of a particular class.
All instances of a class share a common set of properties.

## EXAMPLES

### Example 1: Gets class instances by using a display name
```
PS C:\>Get-SCOMClassInstance -Displayname "Server01.Contoso.Com", "*.contoso.com"
```

This command gets the class instance that has the display name Server01.Contoso.Com and the class instances in the contoso.com domain.

### Example 2: Gets class instances by using a name
```
PS C:\>Get-SCOMClass -Name "*Windows*" | Get-SCOMClassInstance
```

This command gets class instances of classes.
The command uses the **Get-SCOMClass** to get all classes that have "Windows" in their name, and passes the result to the **Get-SCOMClassInstance** cmdlet by using the pipeline operator.
The command gets the class instances for the classes that have Windows in their name.

### Example 3: Gets class instances by using an Id
```
PS C:\>Get-SCOMClassInstance -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd
```

This command gets the class instance that has an Id of 7413b06b-a95b-4ae3-98f2-dac9ff76dabd.

## PARAMETERS

### -Class
Specifies an array of **ManagementPackClass** objects.
To obtain a **ManagementPackClass** object, use the **Get-SCOMClass** cmdlet.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be running on the computer.
If you do not specify a computer, the cmdlet uses the computer for the current management group connection.

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
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

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
Specifies an array of display names of objects.
Values for this parameter depend on which localized management packs you import and the locale of the user that runs Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromEMODisplayNameParameterSetName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Group
Specifies an array of **EnterpriseManagementObject** objects.
To obtain a **EnterpriseManagementObject** object, use the **Get-SCOMGroup** cmdlet. 
For more information, type `Get-Help Get-SCOMGroup`.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies an array of GUIDs of classe instances.
To get the GUID of a class, type `Get-SCOMClassInstance | Format-Table DisplayName, Id`.

```yaml
Type: Guid[]
Parameter Sets: FromEMOIdParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of objects.

```yaml
Type: String[]
Parameter Sets: FromEMONameParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCOMManagementGroupConnection** cmdlet.

A connection object represents a connection to a management server.
The default is the current management group connection.

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

## NOTES

## RELATED LINKS

[Get-SCOMGroup](xref:SystemCenter2016/OperationsManager/v1.0/Get-SCOMGroup.md)

