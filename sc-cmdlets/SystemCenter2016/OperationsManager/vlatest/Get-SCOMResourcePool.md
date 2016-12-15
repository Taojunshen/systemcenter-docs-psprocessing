---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: http://go.microsoft.com/fwlink/?LinkID=199889
schema: 2.0.0
ms.assetid: 3FFD34F8-0D88-4740-B321-323BE5FB894C
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMResourcePool

## SYNOPSIS
Retrieves resource pools in Operations Manager.

## SYNTAX

### Empty (Default)
```
Get-SCOMResourcePool [-EnableAutomaticMembership <Boolean>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassDisplayName
```
Get-SCOMResourcePool [-DisplayName] <String[]> [-EnableAutomaticMembership <Boolean>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCOMResourcePool -Id <Guid[]> [-EnableAutomaticMembership <Boolean>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassName
```
Get-SCOMResourcePool -Name <String[]> [-EnableAutomaticMembership <Boolean>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromMember
```
Get-SCOMResourcePool [-Member] <ComputerHealthService[]> [-EnableAutomaticMembership <Boolean>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromObserver
```
Get-SCOMResourcePool [-Observer] <ComputerHealthService[]> [-EnableAutomaticMembership <Boolean>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMResourcePool** cmdlet retrieves resource pools in System Center 2016 - Operations Manager.
A resource pool enables a collection of management servers to distribute the workload.

## EXAMPLES

### Example 1: Retrieve all resource pools by name
```
PS C:\>Get-SCOMResourcePool -DisplayName "*Management*", "All*"
```

This command uses the **Get-SCOMResourcePool** cmdlet to get the resource pools with Management in their display name and resource pool names that begin with the string All.

### Example 2: Retrieve resource pool by IDs
```
PS C:\>Get-SCOMResourcePool -Id 7413b06b-a95b-4ae3-98f2-dac9ff76dabd, 2ef74789-f9f5-46b0-af70-16d01d4f4577
```

This command uses the **Get-SCOMResourcePool** cmdlet to get the resource pools with the IDs 7413b06b-a95b-4ae3-98f2-dac9ff76dabd and 2ef74789-f9f5-46b0-af70-16d01d4f4577.

### Example 3: Retrieve resource pools by member name
```
PS C:\>$Member = Get-SCOMManagementServer -Name "Member01"
PS C:\> Get-SCOMResourcePool -Member $Member
```

This example retrieves resource pools by display name.

The first command uses the **Get-SCOMManagementServer** cmdlet to get the member with the display name Member01, and stores the result in the $Member variable.

The second command uses the **Get-SCOMResourcePool** cmdlet to return all resource pools for which the value stored in the $Member variable is a member.

### Example 4: Retrieve resource pools by observer name
```
PS C:\>$Observer = Get-SCOMManagementServer -Name "Observer01"
PS C:\> Get-SCOMResourcePool -Observer $Observer
```

This example retrieves resource pools by display name.

The first command uses the **Get-SCOMManagementServer** cmdlet to get the observer with the display name Observer01, and stores the result in the $Observer variable.

The second command uses the **Get-SCOMResourcePool** cmdlet to return all resource pools for which the value stored in the $Observer variable is an observer.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

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
For more information, type "`Get-Help Get-Credential`".If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
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
Specifies an array of display names of an object.
Values of the *DisplayName* parameter may vary depending on which localized management packs a user imports into the management group and the locale of the user who is running Windows PowerShell.

```yaml
Type: String[]
Parameter Sets: FromClassDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -EnableAutomaticMembership
Indicates that the cmdlet returns only those resource pools for which automatic membership is enabled.
These resource pools contain only management servers.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies an array of GUIDs.

An object stores a GUID in the **Id** property for a resource pool.
To obtain the GUID of a resource pool, type "`Get-SCOMResourcePool | Format-Table DisplayName, Id`".

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

### -Member
Specifies an array of objects to include in the resource pool.

Valid objects of a resource pool include management servers and gateway servers.
For information about how to get a management server object, type "`Get-Help Get-SCOMManagementServer`".

```yaml
Type: ComputerHealthService[]
Parameter Sets: FromMember
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies an array of names of an object.

```yaml
Type: String[]
Parameter Sets: FromClassName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Observer
Specifies an array of management server or a gateway management server that is not a member of the resource pool.

To make a resource pool highly available, you must add a minimum of three members to the pool, or two members and one observer.

```yaml
Type: ComputerHealthService[]
Parameter Sets: FromObserver
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To obtain a **Connection** object, use the **Get-SCManagementGroupConnection** cmdlet.

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

[New-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md)

[Remove-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMResourcePool.md)

[Set-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMResourcePool.md)

