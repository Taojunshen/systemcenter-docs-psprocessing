---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CDAA227F-3DA3-46BD-8823-17B403625571
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSQLDeployment

## SYNOPSIS
Gets a SQL Server deployment.

## SYNTAX

### SQLProfile
```
Get-SCSQLDeployment [-VMMServer <ServerConnection>] -SQLProfile <SQLProfile> [-Name <String>]
 [<CommonParameters>]
```

### SQLConfigurationFile
```
Get-SCSQLDeployment [-VMMServer <ServerConnection>] [-SQLConfigurationFile <Script>] [<CommonParameters>]
```

### ID
```
Get-SCSQLDeployment [-VMMServer <ServerConnection>] -ID <Guid> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSQLDeployment** cmdlet gets a Microsoft SQL Server deployment.

## EXAMPLES

### Example 1: Get a specific SQL Server deployment object from an existing SQL Server profile
```
PS C:\> $SQLProfile = Get-SCSQLProfile -Name "SQLProfile01"
PS C:\> Get-SCSQLDeployment -SQLProfile $SQLProfile -Name "SQL Deployment 01"
```

The first command gets the SQL Server profile named SQLProfile01, and then stores that object in the $SQLProfile variable.
This command uses the **Get-SCSQLProfile** cmdlet.

The second command gets the SQL Server deployment named SQL Deployment 01 from the SQL Profile stored in $SQLProfile.

## PARAMETERS

### -ID
Specifies the unique ID of the deployment that this cmdlet gets.

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
Specifies the name of the SQL Server deployment that this cmdlet gets.

```yaml
Type: String
Parameter Sets: SQLProfile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConfigurationFile
Specifies the configuration file for the SQL Server deployment that this cmdlet gets.

```yaml
Type: Script
Parameter Sets: SQLConfigurationFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLProfile
Specifies the SQL Server profile from which this cmdlet gets a SQL Server deployment.

```yaml
Type: SQLProfile
Parameter Sets: SQLProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMMServer
Specifies the VMM server  on which this cmdlet operates.

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

### SQLDeployment
This cmdlet returns a **SQLDeployment** object.

## NOTES

## RELATED LINKS

[Add-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLDeployment.md)

[Remove-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLDeployment.md)

[Set-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLDeployment.md)

[Get-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLProfile.md)

