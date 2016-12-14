---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: 15520B44-C0A2-438D-988B-732C2B675FCA
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCSSASConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCSSASConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/New-SCSSASConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSSASConnection

## SYNOPSIS
Creates a connection to SQL Server Analysis Services.

## SYNTAX

```
New-SCSSASConnection [-VMMServer <ServerConnection>] -ComputerName <String> -InstanceName <String>
 -Port <Int32> -Credential <VMMCredential> [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSSASConnection** cmdlet creates a connection to SQL Server Analysis Services (SSAS) and creates a database named VMMAnalysisServerDB on the SSAS server.

This cmdlet assumes that SSAS and Operations Manager Reporting Server are installed on the same computer.
Therefore, this cmdlet also connects to the SQL Server Reporting Server Web Service to update the credentials for forecasting reports to connect to Analysis Services.

## EXAMPLES

### Example 1: Create a connection to SSAS
```
PS C:\>$SSASCreds = Get-SCRunAsAccount -Name "SSASRunAsAcct"
PS C:\> $SSASSConnection = New-SCSSASConnection -ComputerName "SQLServer01" -InstanceName MSSQLServer -Port 2383 -Credential $SSASCreds
```

The first command gets the Run As account object named SSASRunAsAcct, and then stores that object in the $SSASCreds variable.
This credential needs to be an administrator in both the SQL Server Analysis Service Instance and SQL Server Reporting Instance.

The second command creates an SSAS connection to SQL Server SQLServer01, using the default instance name of MSSQLServer and port 2383.
This cmdlet uses the credentials provided in the Run As account stored in $SSASCreds to create the connection.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
Valid formats are: 

- FQDN (fully qualified domain name) 
- IPv4 or IPv6 address 
- NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or that contains the user name and password of an account that has permission to perform this action.
For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceName
Specifies the SSAS database instance name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobVariable
Specifies a variable in which job progress is tracked and stored.

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

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Specifies the network port to use when adding an object or creating a connection.
Valid values are: 1 to 4095.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### String
This cmdlet returns a **String** object.

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCSSASConnection](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCSSASConnection.md)

[Remove-SCSSASConnection](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCSSASConnection.md)

