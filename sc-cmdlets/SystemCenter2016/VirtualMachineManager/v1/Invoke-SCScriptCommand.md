---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCScriptCommand.md
schema: 2.0.0
ms.assetid: 2480E61B-5352-4C62-93EC-7519241495AF
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Invoke-SCScriptCommand.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Invoke-SCScriptCommand.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Invoke-SCScriptCommand.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Invoke-SCScriptCommand

## SYNOPSIS
Runs a script command on the specified host.

## SYNTAX

### VMHost (Default)
```
Invoke-SCScriptCommand -VMHost <Host> -Executable <String> [-CommandParameters <String>]
 [-ScriptCommandSetting <SCScriptCommandSetting>] [-TimeoutSeconds <Int32>] [-StandardInput <String>]
 [-LibraryResource <CustomResource>] [-RunAsAccount <RunAsAccount>] [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### StorageFileServerNode
```
Invoke-SCScriptCommand -StorageFileServerNode <StorageFileServerNode> -Executable <String>
 [-CommandParameters <String>] [-ScriptCommandSetting <SCScriptCommandSetting>] [-TimeoutSeconds <Int32>]
 [-StandardInput <String>] [-LibraryResource <CustomResource>] [-RunAsAccount <RunAsAccount>]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-SCScriptCommand** cmdlet runs a script command on the specified host.
This cmdlet is only supported on Hyper-V hosts.

## EXAMPLES

### Example 1: Run a script command
```
PS C:\>$VMHost = Get-SCVMHost -ComputerName "VMHost01"
PS C:\> Invoke-SCScriptCommand -VMHost $VMHost -Executable "cmd.exe" -CommandParameters "/C rd C:\test" -TimeoutSeconds 60
```

The first command gets the host object named VMHost01 and stores the object in the $VMHost variable.

The second command runs the executable program named cmd.exe with the specified parameters on the host stored in $VMHost.
In this case, **Invoke-SCScriptCommand** removes the test directory from the c: drive on VMHost01.

## PARAMETERS

### -CommandParameters
Specifies the parameters for a script or executable program.

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

### -Executable
Specifies the name of an executable program.

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

### -LibraryResource
Specifies a resource stored in the VMM library.

```yaml
Type: CustomResource
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

### -RunAsAccount
Specifies a Run As account that contains credentials with permission to perform this action.

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

### -ScriptCommandSetting
Specifies a script command setting object.

```yaml
Type: SCScriptCommandSetting
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StandardInput
Specifies a path to a file that contains standard input information to use with the script command.

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

### -StorageFileServerNode
Specifies a node in a file server cluster.

```yaml
Type: StorageFileServerNode
Parameter Sets: StorageFileServerNode
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TimeoutSeconds
Specifies the amount of time, in seconds, that a process waits before timing out.

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

### -VMHost
Specifies a virtual machine host object.
VMM supports Hyper-V hosts, VMware ESX hosts, and Citrix XenServer hosts.

For more information about each type of host, see the Add-SCVMHost cmdlet.

```yaml
Type: Host
Parameter Sets: VMHost
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### ScriptCommand
This cmdlet returns a **ScriptCommand** object.

## NOTES
* Requires a **VMHost** object, which can be retrieved by using the Get-SCVMHost cmdlet.

## RELATED LINKS

[Add-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Add-SCScriptCommand.md)

[Get-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCScriptCommand.md)

[Get-SCVMHost](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVMHost.md)

[Remove-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Remove-SCScriptCommand.md)

[Set-SCScriptCommand](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCScriptCommand.md)

