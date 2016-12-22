---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7D988B04-342E-4D21-AE1A-7EC3D7DDC4AA
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPXEServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPXEServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCPXEServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCPXEServer

## SYNOPSIS
Removes a PXEServer object from the VMM database.

## SYNTAX

```
Remove-SCPXEServer [-VMMServer <ServerConnection>] [-PXEServer] <PxeServer> -Credential <VMMCredential>
 [-Force] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCPXEServer** cmdlet removes a **PXEServer** object from the Virtual Machine Manager (VMM) database, and uninstalls the VMM agent from the Windows Deployment Services computer.
This cmdlet does not remove the Windows Deployment Services role from the computer.

## EXAMPLES

### Example 1: Remove a VMM PXE server
```
PS C:\> $Credential = Get-SCRunAsAccount "RunAsAcct01"
PS C:\> $PXEServer = Get-SCPXEServer -ComputerName "WDSServer01.Contoso.com"
PS C:\> Remove-SCPXEServer -PXEServer $PXEServer -Credential $Credential -Confirm
```

The first command uses the **Get-Credential** cmdlet to prompt you to supply a user name and password and stores the provided credentials in the $Credential variable.
The account must have local Administrator permissions on the PXE server.

The second command gbets the PXE server object named WDSServer01 and stores the object in the $PXEServer variable.

The third command removes the PXE server object stored in $PXEServer.
As this command is processed, $Credential provides credentials to **Remove-SCPXEServer**, and the *Confirm* parameter prompts you to confirm that you want to remove this PXE server from VMM.

## PARAMETERS

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

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task. 

For more information about the **PSCredential** object, type `Get-Help Get-Credential`. 
For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -PXEServer
Specifies a PXE server object.

```yaml
Type: PxeServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

[Add-SCPXEServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCPXEServer.md)

[Get-SCPXEServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCPXEServer.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

