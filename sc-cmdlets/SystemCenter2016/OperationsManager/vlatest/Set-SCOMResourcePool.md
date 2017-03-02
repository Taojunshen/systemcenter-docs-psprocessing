---
external help file: Microsoft.SystemCenter.OperationsManagerV10.Commands.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E451BE93-EDA5-41A7-B0BB-9954003634A3
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMResourcePool.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMResourcePool.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Set-SCOMResourcePool.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCOMResourcePool

## SYNOPSIS
Changes the properties of a resource pool in Operations Manager.

## SYNTAX

### Empty (Default)
```
Set-SCOMResourcePool [-ResourcePool] <ManagementServicePool[]> [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromMember
```
Set-SCOMResourcePool [-ResourcePool] <ManagementServicePool[]> [-PassThru] [-Member] <ComputerHealthService[]>
 [-Action] <UpdateAction> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromObserver
```
Set-SCOMResourcePool [-ResourcePool] <ManagementServicePool[]> [-PassThru]
 [-Observer] <ComputerHealthService[]> [[-Action] <UpdateAction>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### FromAutoPopulate
```
Set-SCOMResourcePool [-ResourcePool] <ManagementServicePool[]> [-PassThru]
 [-EnableAutomaticMembership] <Boolean> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMResourcePool** cmdlet changes the properties of a resource pool in System Center 2016 - Operations Manager.
A resource pool enables a collection of management servers to distribute the workload.

## EXAMPLES

### Example 1: Add objects to a resource pool
```
PS C:\>$Members = Get-SCOMManagementServer
PS C:\> Get-SCOMResourcePool -DisplayName "Pool01" | Set-SCOMResourcePool -Member $Members -Action "Add"
```

This example changes the properties of a resource pool by adding objects to the resource pool.

The first command uses the **Get-SCOMManagementServer** cmdlet to get all management servers and stores them in the $Members variable.

The second command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with a display name of Pool01, and then uses the **Set-SCOMResourcePool** cmdlet to add the objects stored in the $Members variable to that resource pool.

### Example 2: Remove objects from a resource pool
```
PS C:\>$Member = Get-SCOMManagementServer -Name "Member01"
PS C:\> Get-SCOMResourcePool -DisplayName "Pool01" | Set-SCOMResourcePool -Member $Member -Action "Remove"
```

This example changes the properties of a resource pool by removing objects from the resource pool.

The first command uses the **Get-SCOMManagementServer** cmdlet to get the management server with the display name of Member01 and stores it in the $Member variable.

The second command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with the display name of Pool01 and then uses the **Set-SCOMResourcePool** cmdlet to remove the object stored in the $Member variable from that resource pool.

### Example 3: Add an observer object to a resource pool
```
PS C:\>$Observer = Get-SCOMManagementServer -Name "Observer01"
PS C:\> Get-SCOMResourcePool -DisplayName "Pool01" | Set-SCOMResourcePool -Observer $Observer -Action "Add" -Passthru
```

This example changes the properties of a resource pool by adding an observer object to the resource pool.

The first command uses the **Get-SCOMManagementServer** cmdlet to get the management server named Observer01, and stores the object in the variable named $Observer.

The second command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with the display name of Pool01 and then uses the **Set-SCOMResourcePool** cmdlet to add the Observer object stored in the $Observer variable to that resource pool.

### Example 4: Remove an observer object from a resource pool
```
PS C:\>$Observer = Get-SCOMManagementServer -Name "Observer01"
PS C:\> Get-SCOMResourcePool -DisplayName "Pool01" | Set-SCOMResourcePool -Observer $Observer -Action "Remove" -Passthru
```

This example changes the properties of a resource pool by removing an observer object from the resource pool.

The first command uses the **Get-SCOMManagementServer** cmdlet to get the management server named Observer01, and stores the object in the variable named $Observer.

The second command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with the display name of Pool01 and then uses the **Set-SCOMResourcePool** cmdlet to remove the Observer object stored in the $Observer variable from that resource pool.

### Example 5: Make a display name property change to a resource pool
```
PS C:\>$Pool = Get-SCOMResourcePool -DisplayName "Pool01"
PS C:\>$Pool.DisplayName = "New Pool 02"
PS C:\>$Pool.ApplyChanges()
```

This example changes the properties of a resource pool by changing a property of the resource pool.

The first command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with a display name of Pool01, and stores the object in the variable named $Pool.

The second command changes the value of the DisplayName property for the resource pool stored in the $Pool variable to New Pool 02.

The last command uses the ApplyChanges() method to commit the change to the DisplayName property.

### Example 6: Make a description property change to a resource pool
```
PS C:\>$Pool = Get-SCOMResourcePool -DisplayName "New Pool 02"
PS C:\> $Pool.Description = "Description of New Pool 02"
PS C:\> $Pool.ApplyChanges()
```

This example makes a change to a description property for a resource pool.

The first command uses the **Get-SCOMResourcePool** cmdlet to get the resource pool with a display name of New Pool 02, and stores the object in the variable named $Pool.

The second command changes the value of the Description property for the resource pool stored in the $Pool variable.

The last command uses the ApplyChanges() method to commit the change to the Description property.

## PARAMETERS

### -Action
Specifies an action to take.
When updating the members of a resource pool, specify either Add or Remove.

```yaml
Type: UpdateAction
Parameter Sets: FromMember
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: UpdateAction
Parameter Sets: FromObserver
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
For more information, type "`Get-Help Get-Credential`".

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

### -EnableAutomaticMembership
Indicates that the cmdlet enables automatic membership for the resource pool.
When set to $True, the resource pool contains all management servers, and membership in the pool is automatically managed.
When set to $False, the resource pool can contain management servers, gateway management servers, or both, and membership in the pool is manually managed.

If you change the value from $True to $False, the membership of the pool remains the same until you manually update it.

If the value is changed from $False to $True, all members of the pool are removed, and then the pool is automatically repopulated with all management servers.
The resource pool will be automatically updated as management servers are added and deleted from Operations Manager.
This process can take some time to complete.

```yaml
Type: Boolean
Parameter Sets: FromAutoPopulate
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Member
Specifies an array of objects to include in the resource pool.

Valid members of a resource pool include management servers and gateway servers.
For information about how to get a management server object, type "`Get-Help Get-SCOMManagementServer`".

```yaml
Type: ComputerHealthService[]
Parameter Sets: FromMember
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Observer
Specifies an array of management servers or gateway management servers that are not members of the resource pool.

To make a resource pool highly available, you must add a minimum of three members to the pool, or two members and one observer.

```yaml
Type: ComputerHealthService[]
Parameter Sets: FromObserver
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Indicates that the cmdlet creates or modifies an object that a command can use in the pipeline.
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

### -ResourcePool
Specifies an array of resource pool objects.
For information about how to get a resource pool object, type "`Get-Help Get-SCOMResourcePool`".

```yaml
Type: ManagementServicePool[]
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

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMResourcePool.md)

[New-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/New-SCOMResourcePool.md)

[Remove-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCOMResourcePool.md)

