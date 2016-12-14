---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 3ffd34f8-0d88-4740-b321-323be5fb894c
schema: 2.0.0
ms.assetid: 8317A251-09C9-466A-B38D-58FCA5D2158C
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Invoke-SCXDiscovery.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Invoke-SCXDiscovery.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/OperationsManager/v1/Invoke-SCXDiscovery.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Invoke-SCXDiscovery

## SYNOPSIS
Invokes the discovery operation for the specified configuration of UNIX and Linux computers.

## SYNTAX

### FromHostNameAndResourcePoolParameterSetName
```
Invoke-SCXDiscovery [-WsManCredential <PSCredential>] [-SshCredential <CredentialSet>] -Name <String[]>
 -ResourcePool <ManagementServicePool> [-SshPort <Int32>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromIPRangeAndResourcePoolParameterSetName
```
Invoke-SCXDiscovery [-WsManCredential <PSCredential>] [-SshCredential <CredentialSet>]
 -ResourcePool <ManagementServicePool> -IPRange <IPAddress[]> [-SshPort <Int32>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-SCXDiscovery** cmdlet invokes the discovery operation for the specified configuration of UNIX and Linux computers.

The operation uses an SSH credential object for privileged SSH installation actions and an optional Windows PowerShell credential object for low-privileged WS-Management agent communication.
If the agent has been manually installed on the targeted hosts, only the low-privileged WS-Management credential is required.

The output of this cmdlet is an array of **DiscoveryResult** objects representing the discovery result for each targeted computer for which discovery was attempted.

## EXAMPLES

### Example 1: Discover UNIX and Linux computers within a range of IP addresses
```
PS C:\>$WSCredential = Get-Credential "DavidChew"
PS C:\> $SSHCredential = Get-SCXSSHCredential -UserName "DavidChew" -Key "C:\keys\key22.ppk" -ElevationType sudo
PS C:\> $Pool01 = Get-SCOMResourcePool "pool01"
PS C:\> Invoke-SCXDiscovery -IPRange 192.168.1.50,192.168.1.75 -ResourcePool $Pool01 -WSManCredential $WSCredential -SSHCredential $SSHCredential
```

The first command gets a credential for a user by using the Get-Credential cmdlet.
The command prompts you for authentication, and then stores the results in the $WSCredential variable.

The second command creates a privileged credential for a user by using the Get-SCXSSHCredential cmdlet.
The command stores the result in the $SSHCredential variable.

The third command gets a resource pool named pool01 by using the Get-SCOMResourcePool cmdlet, and then stores it in the $Pool01 variable.

The final command discovers UNIX and Linux computers within a range of IP addresses.

### Example 2: Discover UNIX and Linux computers by name with a non-standard port
```
PS C:\>$WSCredential = Get-Credential "DavidChew"
PS C:\> $SSHCredential = Get-SCXSSHCredential -UserName "DavidChew" -Key c:\keys\DavidChew.ppk -ElevationType sudo
PS C:\> $Pool01 = Get-SCOMResourcePool -DisplayName "pool01"
PS C:\> Invoke-SCXDiscovery -Name "nx1.contoso.com,nx2.contoso.com,nx3.contoso.com" -SSHPort 8022 -ResourcePool $Pool01 -WSManCredential $WSCredential -SSHCredential $SSHCredential
```

The first command gets a credential for a user by using **Get-Credential**.
The command prompts you for authentication, and then stores the results in the $WSCredential variable.

The second command creates a privileged credential for a user by using **Get-SCXSSHCredential**.
The command stores the result in the $SSHCredential variable.

The third command gets a resource pool named pool01 by using **Get-SCOMResourcePool**, and then stores it in the $Pool01 variable.

The final command discovers UNIX and Linux computers by name using a resource pool and specifying a non-standard SSH port.

### Example 3: Discover UNIX and Linux computers by name
```
PS C:\>$Pool = Get-SCOMResourcePool "RP1"
PS C:\> Invoke-SCXDiscovery -Name "nx1.contoso.com,nx2.contoso.com,nx3.contoso.com" -ResourcePool $Pool -WSManCredential "DavidChew"
```

The first command gets a resource pool named RP1 by using **Get-SCOMResourcePool**, and then stores it in the $Pool variable.

The second command discovers UNIX and Linux computers by name where the management agent has already been installed.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be active on the computer.
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
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about credential objects, type `Get-Help Get-Credential`.

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

### -IPRange
Specifies a range of IP Addresses that will be used for discovery.
The *IPRange* must contain two IP Addresses (for example, 192.168.0.1,192.168.0.254).
Either the *IPRange* or *Name* parameters must be specified.

```yaml
Type: IPAddress[]
Parameter Sets: FromIPRangeAndResourcePoolParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a list of valid host names, FQDNs, or IP Addresses (separated by a comma) that will be used for discovery.
Either the *IPRange* or *Name* parameters must be specified.
This parameter is accepted from the pipeline.

```yaml
Type: String[]
Parameter Sets: FromHostNameAndResourcePoolParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePool
Specifies a resource pool of servers, one of which is assigned to be the current management server and the others serving as backup management servers.
This parameter requires a resource pool object and returns only the managed computers in that resource pool.

For information about how to get a resource pool object, type `Get-Help Get-SCOMResourcePool`.

```yaml
Type: ManagementServicePool
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshPort
Specifies the port to use for SSH communication with the host.
If not specified, the default value of 22 is used.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, use the **Get-SCOMManagementGroupConnection** cmdlet.

If this parameter is not specified, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

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

### -SshCredential
Specifies a privileged SSH credential used to perform the agent installation actions.
If this parameter is not specified, the discovery fails unless an agent has been manually installed on the targeted computer.

For information about how to get an SSH credential object, type `Get-Help Get-SCXSSHCredential`.

```yaml
Type: CredentialSet
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WsManCredential
Specifies a credential used for low-privileged agent communication through WS-Management.

Type a user name, such as User01 or enter a **PSCredential** object, such as one that is returned by the Get-Credential cmdlet.
When you type a user name, you are prompted for a password.
For more information, type `Get-Help Get-Credential`.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DiscoveryResult
This cmdlet returns an array of **DiscoveryResult** objects representing the discovery result for each targeted computer for which discovery was planned.

## NOTES

## RELATED LINKS

[Get-SCOMResourcePool](xref:SystemCenter2016/OperationsManager/v1/Get-SCOMResourcePool.md)

[Get-SCXSSHCredential](xref:SystemCenter2016/OperationsManager/v1/Get-SCXSSHCredential.md)

