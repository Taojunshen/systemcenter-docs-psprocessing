---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLibraryServer.md
schema: 2.0.0
ms.assetid: 7FCCB177-A660-4E28-9B47-A28928FB571D
updated_at: 12/14/2016 11:43 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLibraryServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLibraryServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96cd9bd2780eb6b78c540fa00d3b8a4313e3ed40/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1.0/Remove-SCLibraryServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Remove-SCLibraryServer

## SYNOPSIS
Removes a library server from VMM.

## SYNTAX

```
Remove-SCLibraryServer [-LibraryServer] <LibraryServer> -Credential <VMMCredential> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCLibraryServer** cmdlet removes a library server object (and all library objects on that library server) from the Virtual Machine Manager (VMM) database.
Library objects that have a corresponding file (such as .vhd or .vmdk files) stored on the server's file system are not removed from the file system by this cmdlet.

This cmdlet operates as follows: 



- If this library server is also the VMM server, you cannot remove the library server, so the remove library server operation will fail. 


- If this computer is both a library server and a host, this cmdlet removes only the library server feature from VMM, but the computer continues to function as a host. 


- If this computer is only a library server (not also a host or a VMM server), the library server is removed from VMM.

This cmdlet returns the object upon success (with the property MarkedForDeletion set to $True) or returns an error message upon failure.

## EXAMPLES

### Example 1: Remove a library server object from VMM
```
PS C:\>$Creds = Get-Credential
PS C:\> $LibServ = Get-SCLibraryServer -VMMServer "VMMServer1.Contoso.com" -ComputerName "LibraryServer01.Contoso.com"
PS C:\> Remove-SCLibraryServer -LibraryServer $LibServ -Credential $Creds
```

The first command prompts you for credentials.
When the dialog box appears, type the user name and password for either a local Administrator account or a domain account with administrator rights on the library server.

The second command retrieves the library server object named LibraryServer01 on VMMServer01 and stores it in the $LibServ variable.

The third command removes the library server object, and all library shares on this server, from the VMM library.
When the **Remove-SCLibraryServer** cmdlet is used with the *LibraryServer* parameter as shown in this example, you can pass only one library server object to the cmdlet.

### Example 2: Remove multiple library server objects that have a specific string in their name
```
PS C:\>$Creds = Get-Credential
PS C:\> $LibServers = Get-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" | where { $_.Name -match "LibraryServer" }
PS C:\> $LibServers | Remove-SCLibraryServer -Credential $Creds
```

The first command prompts you for credentials.
When the dialog box appears, type the user name and password for either a local Administrator account or a domain account with administrator rights on the library server.

The second command gets all library server objects from VMMServer01 with names that include the string "LibraryServer" and stores the returned objects in the $LibServers variable (an object array).

The third command passes each library server object in $LibServers to **Remove-SCLibraryServer**, which removes each object from VMM.

### Example 3: Remove a highly available library server and all of its nodes
```
PS C:\>$Credential = Get-Credential
PS C:\> $Cluster = Find-SCCluster -ComputerName "HAFileServer01.Contoso.com" -Credential $Credential
PS C:\> Remove-LibraryServer -LibraryServer "HAFileServer01.Contoso.com" -Credential $Credential -RunAsynchronously
PS C:\> ForEach ($Node in $Cluster.ClusterNodes) {Remove-LibraryServer -LibraryServer $Node -Credential $Credential -RunAsynchronously}
```

The first command uses Get-Credential to prompt you to supply a user name and password and stores your credentials in $Credential.
The required credentials for this operation are either a local Administrator account or a domain account with administrator rights on the library server.
The following commands use $Credential to pass your credentials to each cmdlet that requires credentials.

The second command uses the Find-SCCluster cmdlet  to confirm that HAFileServer01 is a highly available file server and stores the cluster object in the $Cluster variable.

The third command removes the highly available file server (by specifying its name) as a library server from VMM.
The command uses the *RunAsynchronously* parameter to return control to the shell immediately (before this command completes) because the last command does not need to wait until after this command finishes.

The last command uses a **ForEach** loop to pass each object stored in $Cluster.ClusterNodes to the **Remove-SCLibraryServer** cmdlet, which removes each node from VMM.
The command uses the *RunAsynchronously* parameter to return control to the shell immediately.
For more information about library servers, type `Get-Help Add-LibraryServer -Detailed`.
For more information about the Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

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
Or, in the case of Restart-SCJob, has permission to complete a restarted task.

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

[Add-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Add-SCLibraryServer.md)

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Get-SCLibraryServer.md)

[Set-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/v1.0/Set-SCLibraryServer.md)

