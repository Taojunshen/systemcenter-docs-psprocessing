---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: E9D27CEE-A713-43A2-BC88-211D22638AE3
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCLibraryServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Add-SCLibraryServer

## SYNOPSIS
Adds a computer as a library server to VMM.

## SYNTAX

```
Add-SCLibraryServer [-VMMServer <ServerConnection>] [-ComputerName] <String> -Credential <VMMCredential>
 [-Description <String>] [-VMHostGroup <HostGroup>] [-JobGroup <Guid>]
 [-EnableUnencryptedFileTransfer <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCLibraryServer** cmdlet adds one or more computers as library servers to Virtual Machine Manager (VMM).
For a computer to be a library server, it must be in the same domain as, or in a trusted domain with, the VMM server.
For VMM library server system requirements, see [Preparing your environment for System Center 2016 - Virtual Machine Manager](http://go.microsoft.com/fwlink/?LinkId=799436) in the TechNet Library at `http://go.microsoft.com/fwlink/?LinkId=799436`.

When you add a computer as a library server to VMM, VMM automatically installs the Virtual Machine Manager Agent software on that server.

The VMM library is made up of two primary components: 

- Library.
The portion of the VMM database that stores objects that represent all library resources. 

- Library Resource Files.
Files that are stored in library shares on one or more physical library servers.
Library resources can be distributed across multiple physical library servers.
Some library objects have files and others do not.

VMM library resources include virtual machine templates, hardware profiles, guest operating system profiles, virtual hard disks (Windows-based .vhd files, Citrix XenServer-based .vhd files or VMware-based .vmdk files), virtual floppy disks (Windows-based .vfd files or VMware-based .flp files), ISO images (.iso files), and scripts.
In addition, you can store virtual machines in the library that you do not want deployed on a host.

Of these resources, templates, hardware profiles, and guest operating system profiles are represented only by objects stored in the library.
The other resources are files stored in the file system on library servers and objects that correspond to those files stored in the library.

## EXAMPLES

### Example 1: Add a library server
```
PS C:\> $Creds = Get-Credential
PS C:\> Add-SCLibraryServer -VMMServer "VMMServer01.Contoso.com" -ComputerName "LibraryServer01.Contoso.com" -Credential $Creds -RunAsynchronously
```

The first command prompts you for credentials.
When the dialog box appears, type the user name and password for either a local Administrator account or a domain account with administrator rights on the library server.

The second command adds the library server object named LibraryServer01 to the library on VMMServer01.

### Example 2: Add a highly available file server with two nodes as a library server
```
PS C:\> $Credential = Get-Credential
PS C:\> $Cluster = Find-SCCluster -ComputerName "HAFileServer01.Contoso.com" -Credential $Credential
PS C:\> ForEach ($Node in $Cluster.ClusterNodes) { Add-SCLibraryServer -ComputerName $Node -Credential $Credential}
PS C:\> Add-SCLibraryServer -ComputerName "HAFileServer01.Contoso.com" -Credential $Credential
PS C:\> Add-SCLibraryShare -SharePath "\\HAFileServer01.Contoso.com\LibShare" -Credential $Credential
```

This example assumes the following: you have created a cluster with at least two nodes, you have created a highly available file server, and you have created a share on the highly available file server (in this example, this is represented by \\HAFIleServer01.Contoso.com\LibShare).

The first command uses **Get-Credential** to prompt you to supply a user name and password and stores your credentials in $Credential.
The required credentials for this operation are a domain account with administrator rights on each node of a failover cluster hosting the highly available file server that you want to add to VMM.

The second command uses the **Find-SCCluster** cmdlet to confirm that HAFileServer01 is a highly available file server and stores the cluster object in the $Cluster variable.

The third command uses a **ForEach** loop to pass each cluster node to **Add-SCLibraryServer**, which adds the nodes as library servers.
For more information about the Windows PowerShell **ForEach** loop statement, type `Get-Help about_ForEach`.

The fourth command uses **Add-SCLibraryServer** to add the highly available file server named HAFileServer01 to VMM as a library server.

The last command uses **Add-SCLibraryShare** to add the specified share on the highly available file server.
For more information about adding library shares, type `Get-Help Add-SCLibraryShare`.

## PARAMETERS

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the PSCredential object, type `Get-Help Get-Credential`.

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

### -VMHostGroup
Specifies a virtual machine host group object.

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

### LibraryServer
This cmdlet returns a **LibraryServer** object.

## NOTES

## RELATED LINKS

[Get-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCLibraryServer.md)

[Remove-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCLibraryServer.md)

[Set-SCLibraryServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCLibraryServer.md)

