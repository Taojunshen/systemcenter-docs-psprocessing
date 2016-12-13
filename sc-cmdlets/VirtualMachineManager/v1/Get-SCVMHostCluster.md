---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCVMHostCluster.md
schema: 2.0.0
ms.assetid: 30FB5A8E-4DFD-431F-9741-EDCFDF62C063
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostCluster.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostCluster.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Get-SCVMHostCluster.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCVMHostCluster

## SYNOPSIS
Gets a host cluster object.

## SYNTAX

### Connection (Default)
```
Get-SCVMHostCluster [-VMMServer <ServerConnection>] [-VMHostGroup <HostGroup>] [-Name <String>] [-ID <Guid>]
 [<CommonParameters>]
```

### VMHostGroup
```
Get-SCVMHostCluster -VMHostGroup <HostGroup> [-Name <String>] [<CommonParameters>]
```

### Name
```
Get-SCVMHostCluster [-VMHostGroup <HostGroup>] -Name <String> [<CommonParameters>]
```

### ID
```
Get-SCVMHostCluster -ID <Guid> [<CommonParameters>]
```

### AssociatedWithStorageArray
```
Get-SCVMHostCluster -HyperConvergedStorageArray <StorageArray> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCVMHostCluster** cmdlet gets one or more host cluster objects from the Virtual Machine Manager (VMM) database.

## EXAMPLES

### Example 1: Get all host clusters managed by a VMM server
```
PS C:\>Get-SCVMHostCluster -VMMServer "VMMServer01.Contoso.com"
```

This command gets all host cluster objects on VMMServer01 and displays information about each host cluster to the user.

### Example 2: Get all host clusters managed by a VMM server and display the host cluster name and virtualization platform for each cluster
```
PS C:\>Get-SCVMHostCluster -VMMServer "VMMServer01.Contoso.com" | Select-Object -Property Name, VirtualizationPlatform
```

This command gets all host cluster objects on VMMServer01 and passes each object to the Select-Object cmdlet, which displays the name and virtualization platform for each host cluster.

### Example 3: Get a host cluster by name
```
PS C:\>Get-SCVMHostCluster -Name "VMHostCluster03.Contoso.com"
```

This command gets the host cluster object named VMHostCluster03 and displays information about the cluster.

### Example 4: Display the object type, methods, and properties for a host cluster managed by VMM
```
PS C:\>Get-SCVMHostCluster -VMMServer "VMMServer01.Contoso.com" | Get-Member
```

This command gets the host cluster objects on VMMServer01 and then passes a host cluster object to the Get-Member cmdlet, which displays the .NET type for a host cluster object and the list of events, methods, and properties associated with a host cluster object.

## PARAMETERS

### -HyperConvergedStorageArray


```yaml
Type: StorageArray
Parameter Sets: AssociatedWithStorageArray
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ID
Specifies the numerical identifier as a globally unique identifier, or GUID, for a specific object.

```yaml
Type: Guid
Parameter Sets: Connection
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Guid
Parameter Sets: ID
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: Connection, VMHostGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Name
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostGroup
Specifies a virtual machine host group object.

```yaml
Type: HostGroup
Parameter Sets: Connection, Name
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: HostGroup
Parameter Sets: VMHostGroup
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: Connection
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

### VMHostCluster
This cmdlet returns a **VMHostCluster** object.

## NOTES

## RELATED LINKS

[Add-SCVMHostCluster](xref:VirtualMachineManager/v1/Add-SCVMHostCluster.md)

[Install-SCVMHostCluster](xref:VirtualMachineManager/v1/Install-SCVMHostCluster.md)

[Move-SCVMHostCluster](xref:VirtualMachineManager/v1/Move-SCVMHostCluster.md)

[Read-SCVMHostCluster](xref:VirtualMachineManager/v1/Read-SCVMHostCluster.md)

[Remove-SCVMHostCluster](xref:VirtualMachineManager/v1/Remove-SCVMHostCluster.md)

[Set-SCVMHostCluster](xref:VirtualMachineManager/v1/Set-SCVMHostCluster.md)

[Test-SCVMHostCluster](xref:VirtualMachineManager/v1/Test-SCVMHostCluster.md)

[Uninstall-SCVMHostCluster](xref:VirtualMachineManager/v1/Uninstall-SCVMHostCluster.md)

