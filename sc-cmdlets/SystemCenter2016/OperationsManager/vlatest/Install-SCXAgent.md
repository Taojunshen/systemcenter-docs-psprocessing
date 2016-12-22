---
external help file: Microsoft.SystemCenter.CrossPlatform.PowerShell.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: D5E8F884-060A-43A5-9AF4-CE521D033413
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Install-SCXAgent.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Install-SCXAgent.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Install-SCXAgent.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Install-SCXAgent

## SYNOPSIS
Installs the Operations Manager agent for discovered UNIX and Linux computers.

## SYNTAX

```
Install-SCXAgent -DiscoveryResult <DiscoveryResult[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Install-SCXAgent** cmdlet installs the Operations Manager agent for discovered UNIX and Linux computers, signs the certificate for WS-Management communication, and registers the agent with Operations Manager for management.
UNIX and Linux computers should be discovered with the Invoke-SCXDiscovery cmdlet.
The output object of the **Invoke-SCXDiscovery** cmdlet is provided as the *DiscoveryResult* input for the **Install-SCXAgent** cmdlet.

For information about discovering UNIX or Linux computers, type Get-Help Invoke-SCXDiscovery.

This cmdlet returns an array of managed UNIX or Linux computer objects that represent the targeted systems that were successfully installed.

## EXAMPLES

### Example 1: Discover UNIX and Linux computers and install the management agent
```
PS C:\>$WSCredential = Get-Credential "DavidChew"
PS C:\> $SSHCredential = Get-SCXSSHCredential -UserName "DavidChew" -Key "C:\keys\key21.ppk" -ElevationType sudo
PS C:\> $Pool01 = Get-SCOMResourcePool -DisplayName "Pool01"
PS C:\> Invoke-SCXDiscovery -IPRange 192.168.1.50,192.168.1.75 -ResourcePool $MyPool -WSManCredential $WSCredential -SSHCredential $SSHCredential | Install-SCXAgent
```

The first command gets a credential for a user by using the Get-Credential cmdlet.
The command prompts you for authentication, and then stores the results in the $WSCredential variable.

The second command creates a privileged credential for a user by using the Get-SCXSSHCredential cmdlet.
The command stores the result in the $SSHCredential variable.

The third command gets a resource pool named Pool01 by using the Get-SCOMResourcePool cmdlet, and then stores it in the $Pool01 variable.

The final command invokes a discovery of UNIX and Linux computers within a range of IP Addresses by using the Invoke-SCXDiscovery cmdlet.
The command passes any discovered computers to the current cmdlet by using the pipeline operator.
The command installs the management agent.

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

### -DiscoveryResult
Specifies the **DiscoveryResult** object to process for management agent installation as returned by the **Invoke-SCXDiscovery** cmdlet.

For more information about discovering targeted systems, type `Get-Help Invoke-SCXDiscovery`.

```yaml
Type: DiscoveryResult[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Unix.Computer[]
This cmdlet returns an array of managed UNIX and Linux computers that were successfully installed.

## NOTES

## RELATED LINKS

[Get-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCXAgent.md)

[Get-SCXSSHCredential](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCXSSHCredential.md)

[Invoke-SCXDiscovery](xref:SystemCenter2016/OperationsManager/vlatest/Invoke-SCXDiscovery.md)

[Remove-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Remove-SCXAgent.md)

[Uninstall-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Uninstall-SCXAgent.md)

[Update-SCXAgent](xref:SystemCenter2016/OperationsManager/vlatest/Update-SCXAgent.md)

