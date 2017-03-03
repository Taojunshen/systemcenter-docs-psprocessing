---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 0917556B-6339-4A88-B898-B11D3D935FBD
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCSQLDeployment

## SYNOPSIS
Adds a SQL Server deployment to a SQL Server profile.

## SYNTAX

```
Add-SCSQLDeployment -AgentServiceRunAsAccount <VMMCredential> -SQLServiceRunAsAccount <VMMCredential>
 [-ReportingServiceRunAsAccount <VMMCredential>] [-DeploymentRunAsAccount <VMMCredential>]
 [-DeploymentTimeoutSeconds <Int32>] [-EnableNamedPipes <Boolean>] [-SARunAsAccount <VMMCredential>]
 [-SecurityMode <String>] [-EnableTCP <Boolean>] [-ProductKey <String>] -SQLProfile <SQLProfile> -Name <String>
 -InstanceID <String> -MediaSource <String> -SQLSysAdminMemberList <String[]> [-SQLConfigurationFile <Script>]
 [-InstanceName <String>] [-MergeSQLAnswerFile <Boolean>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCSQLDeployment** cmdlet adds a Microsoft SQL Server deployment to a SQL Server profile.

## EXAMPLES

### Example 1: Add a SQL Server deployment to a SQL Server profile
```
PS C:\> $SQLProfile = Get-SCSQLProfile -Name "SQLProfile01"
PS C:\> $DeploymentRunAsProfile = Get-SCRunAsProfile -Name "NTSystemRAP"
PS C:\> $SARunAsProfile = Get-SCRunAsProfile -Name "SQLAdminRAP"
PS C:\> $SQLSvcsRunAsProfile = Get-SCRunAsProfile -Name "NTSystemRAP"
PS C:\> Add-SCSQLDeployment -SQLProfile $SQLProfile -Name "SQL Deployment 01" -MediaSource "C:\SQLMedia" -InstanceID "SysPrepSQL" -InstanceName "MSSQLSERVER" -DeploymentTimeoutSeconds 3600 -SQLAuthenticationType "SQLServerAuthentication" -EnableNamedPipes $True -EnableTCP $True -SQLSysAdminMemberList @("Contoso\SQLAdmins") -ProductKey $Null -AgentServiceRunAsProfile $SQLSvcsRunAsProfile -SQLServiceRunAsProfile $SQLSvcsRunAsProfile -DeploymentRunAsProfile $DeploymentRunAsProfile -SARunAsProfile $SARunAsProfile
```

The first command gets the SQL Server profile named SQLProfile01, and then stores that object in the $SQLProfile variable.

The second command gets the **RunAsProfile** named NTSystemRAP, and then stores that object in the $DeploymentRunAsProfile variable.
For more information, type `Get-Help Get-SCRunAsProfile`.
A subsequent command specifies this object to initiate and run the deployment.

The third command gets the **RunAsProfile** named SQLAdminRAP, and then stores that object in the $SARunAsProfile variable.
A subsequent command defines this value as the system administrator credentials for the deployment.

The fourth command gets the **RunAsProfile** named NTSystemRAP, and then stores that object in the $SQLSvcsRunAsProfile variable.
A subsequent command specifies this value as the service account for the SQL Server and SQL Server Agent Windows services,

The final command adds a SQL Server deployment named SQL Deployment 01 to the SQLProfile01 SQL profile.
This command specifies **RunAsProfile** objects that previous commands stored in variables.

## PARAMETERS

### -AgentServiceRunAsAccount
Specifies the Run As account that the SQL Server agent service uses.

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

### -DeploymentRunAsAccount
Specifies the Run As account that this cmdlet uses to install SQL Server.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeploymentTimeoutSeconds
Specifies the amount of time, in seconds, that the SQL Server deployment waits before it times out.

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

### -EnableNamedPipes
Indicates whether remote connections use named pipes.

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

### -EnableTCP
Indicates whether remote connections use TCP/IP.

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

### -InstanceID
Specifies the ID of a SQL Server deployment instance.

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

### -InstanceName
Specifies the name of the SQL Server Analysis Services (SSAS) database instance.

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

### -MediaSource
Specifies a media source for the new SQL Server deployment.

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

### -MergeSQLAnswerFile
Indicates whether this cmdlet merges the answer file together with guest operating system settings.
The default value is $True.
VMM console uses this parameter.
Do not specify this parameter.

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

### -Name
Specifies the name of the SQL Server deployment that this cmdlet adds.

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

### -ProductKey
Specifies the product key for the VMM Server.
The product key is a 25-digit number that identifies the product license.

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

### -ReportingServiceRunAsAccount
Specifies the Run As account that Reporting Services uses.

```yaml
Type: VMMCredential
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

### -SARunAsAccount
Specifies the Run As account for the SQL Server system administrator password.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLConfigurationFile
Specifies the configuration file for the SQL Server deployment that this cmdlet adds.

```yaml
Type: Script
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SQLProfile
Specifies the SQL Server profile to which this cmdlet adds a SQL Server deployment.

```yaml
Type: SQLProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SQLServiceRunAsAccount
Specifies the Run As account that the SQL Server service uses.

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

### -SQLSysAdminMemberList
Specifies an array of users who are SQL Server administrators.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityMode
Specifies the security mode for SQL Server.
Valid values are: WindowsAuthentication and SQLServerAuthentication.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### SQLDeployment
This cmdlet returns a **SQLDeployment** object.

## NOTES

## RELATED LINKS

[Get-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLDeployment.md)

[Get-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLProfile.md)

[Remove-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLDeployment.md)

[Set-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLDeployment.md)

