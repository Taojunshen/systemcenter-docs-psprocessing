---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryServer.md
schema: 2.0.0
ms.assetid: 7C5329CA-1202-45B7-81A5-BBD8448BAB32
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCLibraryServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCLibraryServer

## SYNOPSIS
Sets the properties of a VMM library server.

## SYNTAX

### Default (Default)
```
Set-SCLibraryServer [-LibraryServerManagementCredential <RunAsAccount>] [-LibraryServer] <LibraryServer>
 [-Description <String>] [-VMHostGroup <HostGroup>] [-ClearVMHostGroup] [-JobGroup <Guid>]
 [-EnableUnencryptedFileTransfer <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

### VMNetwork
```
Set-SCLibraryServer [-LibraryServerManagementCredential <RunAsAccount>] [-LibraryServer] <LibraryServer>
 [-Description <String>] [-VMHostGroup <HostGroup>] [-ClearVMHostGroup] [-JobGroup <Guid>]
 -VMNetworks <VMNetwork[]> [-EnableUnencryptedFileTransfer <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### AddVMNetwork
```
Set-SCLibraryServer [-LibraryServerManagementCredential <RunAsAccount>] [-LibraryServer] <LibraryServer>
 [-Description <String>] [-VMHostGroup <HostGroup>] [-ClearVMHostGroup] [-JobGroup <Guid>]
 -AddVMNetwork <VMNetwork[]> [-EnableUnencryptedFileTransfer <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### RemoveVMNetwork
```
Set-SCLibraryServer [-LibraryServerManagementCredential <RunAsAccount>] [-LibraryServer] <LibraryServer>
 [-Description <String>] [-VMHostGroup <HostGroup>] [-ClearVMHostGroup] [-JobGroup <Guid>]
 -RemoveVMNetwork <VMNetwork[]> [-EnableUnencryptedFileTransfer <Boolean>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCLibraryServer** cmdlet sets the properties of a Virtual Machine Manager (VMM) library server.
You can also use this cmdlet as part of a job group, when used with the Add-SCLibraryShare cmdlet, to add a set of library shares.

## EXAMPLES

### Example 1: Change the description of a library server
```
PS C:\>$LibServer = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "LibraryServer01.Contoso.com"
PS C:\> Set-SCLibraryServer -LibraryServer $LibServer -Description "Library server for Production"
```

The first command gets the library server object named LibraryServer01 on VMMServer01 and stores it in the $LibServer variable.

The second command changes the description for FileServer01 to "Library server for Production."

### Example 2: Update the description for a library server
```
PS C:\>$LibServer = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "LibraryServer01.Contoso.com"
PS C:\> Set-SCLibraryServer -LibraryServer $LibServer -Description "The library server is used by the Seattle office."
```

The first command gets the library server object named LibraryServer01 on VMMServer01 and stores it in the $LibServer variable.

The second command updates the description for the library server object stored in the $LibServer variable.

### Example 3: Add a VM network to a library server
```
PS C:\>$VMNetwork = Get-SCVMNetwork -Name "VMNetwork01"
PS C:\> Get-SCLibraryServer -ComputerName "LibraryServer01.Contoso.com" | Set-SCLibraryServer -AddVMNetwork $VMNetwork
```

The first command gets the VM network object named VMNetwork01 and stores the object in the $VMNetwork variable.

The second command gets the library server object named LibraryServer01 and uses the pipeline operator to pass the object to the **Set-SCLibraryServer** cmdlet, which adds VMNetwork01 to the library server.

## PARAMETERS

### -AddVMNetwork
Specifies that one or more VM networks has network connectivity to the specified library server when used in conjunction with **Set-SCLibraryServer**.

```yaml
Type: VMNetwork[]
Parameter Sets: AddVMNetwork
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClearVMHostGroup
Resets the host group association for the library server.

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

### -Description
Specifies a description for the library server.

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

### -EnableUnencryptedFileTransfer
Indicates, when set to True, that network file transfers do not require encryption.
Allowing unencrypted network file transfers can improve performance if neither the source host nor the destination host requires encryption.

Use this parameter to: 


- Enable unencrypted file transfers into, or out of, the library. 

- Enable unencrypted file transfers into, out of, or within a host group.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: AllowUnencryptedTransfers

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -LibraryServer
Specifies a VMM library server object.

```yaml
Type: LibraryServer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LibraryServerManagementCredential
Specifies a Run As account for the VMM library.

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

### -RemoveVMNetwork
Removes network connectivity for one or more VM networks from the specified library server when used in conjunction with Set-SCVMLibraryServer.

```yaml
Type: VMNetwork[]
Parameter Sets: RemoveVMNetwork
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

### -VMHostGroup
Specifies a virtual machine host group object or an array of host group objects.

```yaml
Type: HostGroup
Parameter Sets: (All)
Aliases: LibraryGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMNetworks
Specifies that one or more VM networks have network connectivity to the specified library server when used in conjunction with Set-SCVMLibraryServer.

```yaml
Type: VMNetwork[]
Parameter Sets: VMNetwork
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

### LibraryServer
This cmdlet returns a **LibraryServer** object.

## NOTES
* Requires a VMM library server object, which can be retrieved by using the Get-SCLibraryServer cmdlet.

## RELATED LINKS

[Add-SCLibraryServer](xref:VirtualMachineManager/v1/Add-SCLibraryServer.md)

[Get-SCLibraryServer](xref:VirtualMachineManager/v1/Get-SCLibraryServer.md)

[Remove-SCLibraryServer](xref:VirtualMachineManager/v1/Remove-SCLibraryServer.md)

