---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 350A270A-A6B5-4049-BCAB-E18A7C4E56A0
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCVMMServer

## SYNOPSIS
Connects to a VMM management server if a connection does not already exist, or connects to a different VMM management server.

## SYNTAX

```
Get-SCVMMServer [-ComputerName] <String> [-TCPPort <Int32>] [-ConnectAs <Profile>] [-UserRoleName <String>]
 [-Credential <PSCredential>] [-RetainObjectCache] [-RetainDeletedObjects] [-AllowJobGC] [-SetAsDefault]
 [-ForOnBehalfOf] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMMServer** cmdlet connects to a Virtual Machine Manager (VMM) management server if a connection does not already exist and retrieves the server object from the VMM database.
The default port used to connect to a VMM server is TCP port 8100.

If you have created a connection to a VMM management server using the user interface (UI), when you open a VMM command shell, that command shell automatically connects to the same VMM management server.
If you have not previously connected to the VMM managment server using the UI, you need to use **Get-SCVMMServer** to establish a connection.
Note that if you connect to a VMM management server only using the VMM command shell, you must use the *SetAsDefault* parameter to retain the connection from session to session, or re-connect to the VMM server each time you open a new VMM command shell session.

You can also use **Get-VMMServer** to connect to a different VMM management server.

After a connection to the VMM management server is established, all future commands run at the VMM command shell command line that require the VMM server object will automatically use the existing connection until you close that VMM command shell window.

The VMM service running on the VMM management server supports the VMM database.
This database is stored in Microsoft SQL Server either on the VMM management server itself or on a separate server running SQL Server.

The VMM service enables you to manage your virtual environment, including host servers (which host virtual machines), library servers (which store VMM library resources), and virtual machines deployed on a host or stored in the library.

For more information about connecting to the VMM management server, type `Get-Help about_VMM_2016_Connecting_to_the_VMM_Server`.

## EXAMPLES

### Example 1: Connect to a VMM server
```
PS C:\> Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
```

This command connects to the VMM server named VMMServer01 located in the Contoso domain and gets the server object from the VMM database.

### Example 2: Connect to a VMM server through a specific port
```
PS C:\> Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com" -TCPPort 8100
```

This command connects over TCP port 8100 to the VMM server named VMMServer01 located in the Contoso domain.

### Example 3: Connect to a VMM server and get its .NET object type, methods, and properties
```
PS C:\> $VMMServer = Get-SCVMMServer -ComputerName "VMMServer01.Contoso.com"
PS C:\> $VMMServer | Get-Member
PS C:\> $VMMServer | Get-Member | Format-List
```

The first command gets the VMM server object named VMMServer01 and stores the object in the $VMMServer variable.

The second command passes the VMM server object stored in $VMMServer to the **Get-Member** cmdlet, which retrieves and displays the following: 


- TypeName: The .NET type name of the VMM server object: **Microsoft.SystemCenter.VirtualMachineManager.Remoting.ServerConnection**

- MemberType: A list containing the name and definition for each event,
  method, and property associated wtih this object type.

The third command retrieves and displays the same information as the second command, except that it pipes the output to the Format-List cmdlet to display the complete definition for each method and each property for the VMM server object.

### Example 4: Connect to a different VMM server with a different user role
```
PS C:\> Get-SCVMMServer -ComputerName "VMMServer02.Contoso.com" -ConnectAs "DelegatedAdmin"
```

This command connects to the VMM server named VMMServer02 located in the Contoso domain using the DelegatedAdmin user role.

## PARAMETERS

### -AllowJobGC
Indicates that garbage collection is allowed for jobs.

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

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectAs
Specifies the VMM user role to use, if the user is a member of more than one role, when connecting to the VMM management server from the VMM command shell.
The acceptable values for this parameter are:

- Administrator
- DelegatedAdmin
- ReadOnlyAdmin
- SelfServiceUser

VMM Administrators can manage all VMM objects.
Delegated administrators and self-service users can access and change only the objects that are within the scope of their user roles.
Read-Only administrators can only view the properties of existing objects; they cannot create new objects or change the properties of existing objects.

```yaml
Type: Profile
Parameter Sets: (All)
Aliases: 
Accepted values: Administrator, DelegatedAdmin, TenantAdmin, SelfServiceUser, ReadOnlyAdmin

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

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

### -ForOnBehalfOf
Indicates that an administrator is able to use *OnBehalfOf* parameters, when available, for VMM cmdlets.
This parameter is primarily used for Service Provider Foundation connections to VMM.

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

### -RetainDeletedObjects
Specifies that objects in the cache that are marked for deletion will be preserved.
You might need this parameter only if you create a user interface on top of the VMM command shell.

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

### -RetainObjectCache
Indicates that the objects in the cache will remain in memory and will not be reclaimed by garbage collection.
You might need this parameter if you create a user interface on top of the VMM command shell.

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

### -SetAsDefault
Indicates, when set to $True, that the VMM command shell connects to the specified VMM management server for this session and retains that connection for future sessions.

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

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Port

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRoleName
Specifies the name of a user role.
Types of user roles that are named include: 

- Delegated Administrator
- Read-Only Administrator
- Self-Service User

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Backup-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Backup-SCVMMServer.md)

[Set-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMServer.md)

