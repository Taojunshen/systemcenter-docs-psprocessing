---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCOpsMgrConnection.md
schema: 2.0.0
ms.assetid: 546155B5-92EB-4893-9662-D9E7E72BC10D
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCOpsMgrConnection.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCOpsMgrConnection

## SYNOPSIS
Creates a connection to an Operations Manager management group.

## SYNTAX

```
New-SCOpsMgrConnection [-EnablePRO <Boolean>] [-VMMServer <ServerConnection>] -OpsMgrServer <String>
 [-UseVMMServerServiceAccount] [-OpsMgrServerCredential <RunAsAccount>] -VMMServerCredential <PSCredential>
 [-EnableMaintenanceModeIntegration <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCOpsMgrConnection** cmdlet creates a connection between the Virtual Machine Manager (VMM) management server that you are currently connected to and an Operations Manager management group.

Before creating a connection to an Operations Manager management server, you must install the Operations Manager management console on your VMM management server and install the following management packs in Operations Manager: 



- SQL Server Core Library version 6.0.5000.0 or later management pack

- Windows Server Internet Information Services Library version 6.0.5000.0 or later management pack

- Windows Server Internet Information Services 2003 version 6.0.5000.0 or later management pack

- Windows Server Internet Information Services 7 version 6.0.6539.0 or later management pack

## EXAMPLES

### Example 1: Create a connection to an Operations Manager management server
```
PS C:\>$OMCreds = Get-SCRunAsAccount -Name "OpsMgrServerAccount"
PS C:\> $VMMCreds = Get-Credential
PS C:\> New-SCOpsMgrConnection -OpsMgrServer "OpsMgrServer01.Contoso.com" -OpsMgrServerCredential $OMCreds -VMMServerCredential $VMMCreds
```

The first command gets the Run As account object named OpsMgrServerAccount and stores the object in the $OMCreds variable.
The credentials provided in the Run As account must be a member of the Administrators user role on the Operations Manager management server.

The second command prompts you to for credentials, and stores the credentials you provide in the $VMMCreds variable.
The account you provide must be a member of the Administrator user role on the VMM management server.

The last command creates a connection between the VMM management server that you are currently connected to and OpsMgrServer01 using the credentials obtained in the first two commands.

## PARAMETERS

### -EnableMaintenanceModeIntegration
Indicates whether maintenance mode integration is enabled for this connection.

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

### -EnablePRO
Indicates whether PRO is enabled for this connection.

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

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

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

### -OpsMgrServer
Specifies the fully qualified domain name (FQDN) of the System Center Operations Manager management server to which VMM connects.

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

### -OpsMgrServerCredential
Specifies the credentials that VMM uses to connect to the Operations Manager management group.
The specified account must be an administrator on the Operations Manager computer (a member of the Builtin\Administrators group).

```yaml
Type: RunAsAccount
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

### -UseVMMServerServiceAccount
Specifies the service account that VMM uses to connect to Operations Manager.

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

### -VMMServerCredential
Specifies the credentials that Operations Manager uses to connect with VMM.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### OpsMgrConnection
This cmdlet returns an **OpsMgrConnection** object.

## NOTES

## RELATED LINKS

[Get-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOpsMgrConnection.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Remove-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCOpsMgrConnection.md)

[Set-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCOpsMgrConnection.md)

[Write-SCOpsMgrConnection](xref:SystemCenter2016/VirtualMachineManager/vlatest/Write-SCOpsMgrConnection.md)

