---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E6D0443D-595C-4629-BD64-DC2480262D10
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUpdateServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUpdateServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCUpdateServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCUpdateServer

## SYNOPSIS
Adds a WSUS server to VMM.

## SYNTAX

```
Add-SCUpdateServer [-VMMServer <ServerConnection>] [-ComputerName] <String> -TCPPort <UInt32>
 -Credential <VMMCredential> [-UseSSLConnection] [-StartUpdateServerSync] [-DisableUpdateServerConfiguration]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCUpdateServer** cmdlet adds a Microsoft Windows Server Update Services (WSUS) server to Virtual Machine Manager (VMM).
Adding a WSUS server integrates VMM and WSUS setup and enables the update management feature.

## EXAMPLES

### Example 1: Add an update server
```
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> Add-SCUpdateServer -ComputerName "WSUSComputer01" -TCPPort 80 -Credential $Credential
```

The first command gets the Run As account named RunAsAccount01, and then stores that object in the $Credential variable.

The second command adds update server WSUSComputer01 to VMM.
The command enable update servicing functionality.
This command specifies $Credential Run As account credentials for **Add-SCUpdateServer**.

## PARAMETERS

### -ComputerName
Specifies the name of a computer.
The acceptable values for this parameter are:

- Fully qualified domain name (FQDN) 
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

### -Credential
Specifies a credential object that contains the user name and password of an account that has permission to perform this action.

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

### -DisableUpdateServerConfiguration
Indicates that this cmdlet disables update server configuration.

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

### -StartUpdateServerSync
Indicates that this cmdlet starts update server synchronization.

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
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSSLConnection
Indicates that the update server uses a Secure Sockets Layer (SSL) connection.

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
Specifies the VMM server to which this cmdlet adds an update server.

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

### UpdateServer
This cmdlet returns an **UpdateServer** object.

## NOTES

## RELATED LINKS

[Get-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCUpdateServer.md)

[Remove-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCUpdateServer.md)

[Set-SCUpdateServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCUpdateServer.md)

