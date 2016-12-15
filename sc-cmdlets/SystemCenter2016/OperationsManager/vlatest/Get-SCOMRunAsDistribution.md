---
external help file: OperationsManager-help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239450
schema: 2.0.0
ms.assetid: A5EAC072-59E6-41A8-AD74-6A7F8684B936
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsDistribution.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsDistribution.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsDistribution.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCOMRunAsDistribution

## SYNOPSIS
Gets the distribution policy of an Operations Manager Run As account.

## SYNTAX

```
Get-SCOMRunAsDistribution [-RunAsAccount] <SecureData[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCOMRunAsDistribution** cmdlet gets the distribution policy of a System Center 2016 - Operations Manager Run As account.
Distribution policies determine which computers receive a Run As account credential.

Due to the default formatting behavior of Windows PowerShell, the console does not always display the list of approved distribution computers.
To see the full list, save the output of this cmdlet to a variable, then inspect the **SecureDistribution** property of the **SCOMRunAsDistribution** object that is stored in the variable.

## EXAMPLES

### Example 1: Get the distribution policy for an account
```
PS C:\>Get-SCOMRunAsAccount "Contoso\Administrator" | Get-SCOMRunAsDistribution
```

This command displays the distribution policy for the Contoso\Administrator account.

### Example 2: Get systems approved for distribution in a distribution policy
```
PS C:\>Get-SCOMRunAsAccount "Contoso\Administrator" | Get-SCOMRunAsDistribution | Tee-Object -Variable Distribution
PS C:\> $Distribution.SecureDistribution
```

This example displays the distribution policy for an account and lists the systems that are approved for distribution.

The first command gets the Contoso\Administrator account and passes that account to the **Get-SCOMRunAsDistribution** by using the pipeline operator.
The command uses the pipeline operator to pass the distribution policy to the **Tee-Object** cmdlet, which displays it to the console, as well as saving it in the $Distribution variable.
For more information, type `Get-Help Tee-Object`.

The second command displays the systems approved for distribution.

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

### -RunAsAccount
Specifies an array of **SecureData** objects that represent Run As accounts.
To obtain a **SecureData** object, use the **Get-SCOMRunAsAccount** cmdlet.
This account cannot be part of a Run As profile.

```yaml
Type: SecureData[]
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCOMRunAsAccount](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCOMRunAsAccount.md)

[Set-SCOMRunAsDistribution](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCOMRunAsDistribution.md)

