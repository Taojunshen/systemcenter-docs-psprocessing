---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239455
schema: 2.0.0
ms.assetid: FCF3AB36-F386-49EB-B9EC-D737F0D4ABE0
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMRunAsDistribution.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMRunAsDistribution.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Set-SCOMRunAsDistribution.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCOMRunAsDistribution

## SYNOPSIS
Sets the distribution policy of a Run As account for Operations Manager.

## SYNTAX

### LessSecure
```
Set-SCOMRunAsDistribution [-RunAsAccount] <SecureData> [-LessSecure] [-PassThru] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### MoreSecure
```
Set-SCOMRunAsDistribution [-RunAsAccount] <SecureData> [-MoreSecure] [-SecureDistribution <Object[]>]
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Security
```
Set-SCOMRunAsDistribution [-RunAsAccount] <SecureData> -Security <String> [-SecureDistribution <Object[]>]
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCOMRunAsDistribution** cmdlet sets the distribution policy of a Run As account for System Center 2016 - Operations Manager.
Distribution policies determine which computers receive a credential for a Run As account.
By default, new accounts have the more secure distribution with no approved systems.

## EXAMPLES

### Example 1: Specify a less secure distribution
```
PS C:\>Get-SCOMRunAsAccount -Name "Contoso\LowPriv" | Set-SCOMRunAsDistribution -LessSecure
```

This command sets the Contoso\LowPriv account for less secure distribution, so that Operations Manager distributes the credential automatically to all managed computers.
The command uses the **Get-SCOMRunAsAccount** cmdlet to get the specified account and passes it to the **Set-SCOMRunAsDistribution** cmdlet by using the pipeline operator.
The command specifies the *LessSecure* parameter.

### Example 2: Specify a more secure distribution without approved systems
```
PS C:\>Get-SCOMRunAsAccount -Name "Contoso\LowPriv" | Set-SCOMRunAsDistribution -MoreSecure
```

This command sets the Contoso\LowPriv account for more secure distribution, with no approved systems.
The command uses the **Get-SCOMRunAsAccount** cmdlet to get the specified account and passes it to the **Set-SCOMRunAsDistribution** cmdlet by using the pipeline operator.
The command specifies the *MoreSecure* parameter.

### Example 3: Specify a more secure distribution to a collection
```
PS C:\>$Distribution = (Get-SCOMAgent -Name "*.contoso.com") + (Get-SCOMManagementServer) + (Get-SCOMResourcePool -DisplayName "Contoso Monitoring Pool")
PS C:\> Get-SCOMRunAsAccount "Contoso\LowPriv" | Set-SCOMRunAsDistribution -MoreSecure -SecureDistribution $Distribution
```

This example sets the Contoso\LowPriv account for more secure distribution to a collection of pools, agents, and servers, so that only specified pools, agents, and servers get the distribution.

The first command gets the pools, agents, and servers to receive more secure distribution and stores them in the $Distribution variable .

The second command gets pools, agents, and servers that have less secure distribution and passes them to the **Set-SCOMRunAsDistribution** cmdlet by using the pipeline operator.
That cmdlet assigns them more secure distribution.

### Example 4: Specify less secure distribution for a new Run As account
```
PS C:\>Add-SCOMRunAsAccount -Windows -Name "NewAccount" -Credential (Get-Credential) | Set-SCOMRunAsDistribution -MoreSecure -SecureDistribution (Get-SCOMAgent)
```

This command creates a Run As account for Windows and approves it for distribution to all agents.
The command uses the **Add-SCOMRunAsAccount** cmdlet to add the account NewAccount with the credential that the **Get-Credential** cmdlet creates. 
It then passes the result to the **Set-SCOMRunAsDistribution** cmdlet by using the pipeline operator.

### Example 5: Copy a more secure distribution policy to a different account
```
PS C:\>$MonitoringAcct = Get-SCOMRunAsAccount "Contoso\Monitoring"
PS C:\> Get-SCOMRunAsAccount "Contoso\Administrator" | Get-SCOMRunAsDistribution | Set-SCOMRunAsDistribution -RunAsAccount $MonitoringAccount
```

This example copies the secure distribution policy from the Contoso\Administrator account to the Contoso\Monitoring account.

The first command uses the **Get-SCOMRunAsAccount** cmdlet to get the Contoso\Monitoring account and stores it in the $MonitoringAcct variable.

The second command uses the **Get-SCOMRunAsAccount** cmdlet to get the Contoso\Administrator account and passes it to the **Get-SCOMRunAsDistribution** cmdlet by using the pipeline operator.
The command passes the result to the **Set-SCOMRunAsDistribution** cmdlet to copy the result to the Contoso\Monitoring account.

## PARAMETERS

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The System Center Data Access service must be started on the computer.
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

### -LessSecure
Indicates that Operations Manager distributes the credential automatically to all managed computers.

```yaml
Type: SwitchParameter
Parameter Sets: LessSecure
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MoreSecure
Indicates that Operations Manager distributes the credential only to systems that the *SecureDistribution* parameter specifies.

```yaml
Type: SwitchParameter
Parameter Sets: MoreSecure
Aliases: 

Required: True
Position: Named
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

### -RunAsAccount
Specifies an array of **SecureData** objects that represent Run As accounts.
To obtain a **SecureData** object, use the **Get-SCOMRunAsAccount** cmdlet.
This account cannot be part of a Run As profile.

```yaml
Type: SecureData
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

### -SecureDistribution
Specifies an array of objects that represent systems that the cmdlet authorizes for distribution.

This parameter list can contain only the following types of items:

- Agents.
Objects that the **Get-SCOMAgent** cmdlet returns.
The cmdlet authorizes this account to the agent for distribution.
- Management servers.
Objects that the **Get-SCOMManagementServer** cmdlet returns.
The cmdlet authorizes this account to the agent for distribution.
- Pools.
Objects that the **Get-SCOMResourcePool** cmdlet returns.
The cmdlet authorizes this account to the agent for distribution.
- Health service instances.
Objects that the **Get-SCOMClassInstance** cmdlet returns and that have a managed type of **HealthService**.
The cmdlet authorizes this health service to the agent for distribution.

Passing output from the **Get-SCOMRunAsDistribution** cmdlet as input to **Set-SCOMRunAsDistribution** by using the pipeline operator automatically populates this parameter.

```yaml
Type: Object[]
Parameter Sets: MoreSecure, Security
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Security
Specifies the security level.
The acceptable values for this parameter are: 

- MoreSecure
- LessSecure

Passing output from the **Get-SCOMRunAsDistribution** cmdlet as input to **Set-SCOMRunAsDistribution** by using the pipeline operator automatically populates this parameter.

```yaml
Type: String
Parameter Sets: Security
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[Get-SCOMAgent](xref:OperationsManager/v1/Get-SCOMAgent.md)

[Get-SCOMClassInstance](xref:OperationsManager/v1/Get-SCOMClassInstance.md)

[Get-SCOMManagementServer](xref:OperationsManager/v1/Get-SCOMManagementServer.md)

[Get-SCOMResourcePool](xref:OperationsManager/v1/Get-SCOMResourcePool.md)

[Get-SCOMRunAsAccount](xref:OperationsManager/v1/Get-SCOMRunAsAccount.md)

[Get-SCOMRunAsDistribution](xref:OperationsManager/v1/Get-SCOMRunAsDistribution.md)

