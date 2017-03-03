---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0B5A6BE3-C842-4750-800A-8EAE5FFCBE79
updated_at: 12/22/2016 11:19 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Backup-SCVMMServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Backup-SCVMMServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/d74e247404a4c865a6c8da735e1b4d296bcb074e/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Backup-SCVMMServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Backup-SCVMMServer

## SYNOPSIS
Backs up the Virtual Machine Manager database.

## SYNTAX

```
Backup-SCVMMServer -Path <String> [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Backup-SCVMMServer** cmdlet backs up the Virtual Machine Manager (VMM) database on a VMM server to a local folder or to a remote network share.
The folder to which you back up the database must be accessible to the SQL Server.

To Determine Whether SQL Server is Local or on a Remote Server


If you do not know whether the VMM database is stored locally or on a remote server running Microsoft SQL Server, do the following: 


1.
On the VMM server, open the Registry Editor. 
2.
Navigate to HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft System Center Virtual Machine Manager Server\Settings\Sql
3.
Look at the value for OnRemoteServer: 


    -- If it is set to 0, the database is on the local VMM server. 

    -- If it is set to 1, the database is on a remote SQL server.

Restoring the Backed-up Database


After you use the **Backup-SCVMMServer** cmdlet to back up the VMM database (see Examples 1 and 2), you can use the SCVMMRecover.exe command to restore the database (see Example 3).
This command, which is not a Windows PowerShell cmdlet, is installed with VMM.
By default, SCVMMRecover.exe is installed at \<%system-drive%\>\Program Files\Microsoft System Center 2016\Virtual Machine Manager\bin.

Important: To back up and restore a server functioning as a virtual machine host or as a library server in a VMM environment, use your standard server backup and restore procedures.

## EXAMPLES

### Example 1: Back up the VMM database to a local folder
```
PS C:\> Backup-SCVMMServer -VMMServer "VMMServer01.Contoso.com" -Path "D:\VMMBackups"
```

This command backs up the VMM database on the VMM server named VMMServer01 to the specified path.

Notes: 

- **Backup-SCVMMServer** must back up the database to a server running SQL Server.
This example assumes that SQL Server (for the VMM database) is installed on VMMServer01 rather than on a remote server. 

- When you back up the database to a local folder, the folder must be write-accessible to the SQL Server service.

### Example 2: Back up the VMM database to a network share
```
PS C:\> Backup-SCVMMServer -VMMServer "VMMServer01.Contoso.com" -Path "\\SQLServer01\VMMBackups"
```

This command backs up the VMM database on the VMM server named VMMServer01 to the specified share on a server named SQLServer01.

Important: 


- **Backup-SCVMMServer** must back up the database to a server running SQL Server, so this example assumes that SQL Server (for the VMM database) is installed on SQLServer01. 
- When you back up the database to a remote share, the share must be write-accessible to the SQL Server service.

### Example 3: Restore the VMM database
```
C:\> SCVMMRecover.exe -Path <%backup-folder-path%>\<%backup-file-name%>.bak -Confirm
```

This example demonstrates the use of SCVMMRecover.exe, and not a PowerShell cmdlet.
You must open a command prompt window (not a PowerShell window) and use the SCVMMRecover.exe command that is installed with VMM to perform this operation.
You must run SCVMMRecover.exe locally on the VMM server on which you want to restore the database.
SCVMMRecover.exe does not work with a highly available VMM installation.

This example restores the VMM database to the VMM server where: 



\<%backup-folder-path%\> is the path on the server running SQL Server where the .bak file is saved. 
\<%backup-file-name%\> is the name of the .bak file that was created during the backup operation.

This example assumes that SCVMMRecover.exe is installed in the default location for VMM at \<%system-drive%\>\Program Files\Microsoft System Center 2016\Virtual Machine Manager\bin\SCVMMRecover.exe

## PARAMETERS

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

### -Path
Specifies the destination path for the operation. 

Example formats: 

- Local path: `-Path "F:\"`
- UNC path: `-Path "\\Library\Templates"`
- Volume GUID path: `-Path "\\?\Volume{4703c1ea-8ae7-11db-b473-00123f7603e3}\"`
- VMware ESX path: `-Path "\[storage1\]\MyVMwareFolderForVMs\MyVM.vmx"`
- Citrix XenServer path: `-Path "Local storage\[99b6212f-b63d-c676-25f9-d6c460992de7\]"`

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

### VMMServer
This cmdlet returns a **VMMServer** object.

## NOTES

## RELATED LINKS

[Get-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVMMServer.md)

[Set-SCVMMServer](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVMMServer.md)

