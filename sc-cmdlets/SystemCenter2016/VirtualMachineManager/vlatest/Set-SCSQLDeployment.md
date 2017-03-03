---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: BE67E878-FA85-45C1-98BC-A3F97D26D3F5
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLDeployment.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLDeployment.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCSQLDeployment.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-SCSQLDeployment

## SYNOPSIS
Modifies a SQL Server deployment.

## SYNTAX

```
Set-SCSQLDeployment [-AgentServiceRunAsAccount <VMMCredential>] [-SQLServiceRunAsAccount <VMMCredential>]
 [-SQLConfigurationFile <Script>] [-ReportingServiceRunAsAccount <VMMCredential>]
 [-DeploymentRunAsAccount <VMMCredential>] [-DeploymentTimeoutSeconds <Int32>] [-EnableNamedPipes <Boolean>]
 [-SARunAsAccount <VMMCredential>] [-SecurityMode <String>] [-EnableTCP <Boolean>] [-ProductKey <String>]
 [-SQLDeployment] <SQLDeployment> [-Name <String>] [-InstanceID <String>] [-MediaSource <String>]
 [-SQLSysAdminMemberList <String[]>] [-InstanceName <String>] [-MergeSQLAnswerFile <Boolean>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCSQLDeployment** cmdlet modifies a Microsoft SQL Server deployment.

## EXAMPLES

### Example 1: Modify an existing SQL Server deployment
```
PS C:\> $SQLProfile = Get-SCSQLProfile -Name "SQLProfile01"
PS C:\> $SQLDeployment = Get-SCSQLDeployment -SQLProfile $SQLProfile -Name "SQL Deployment 01"
PS C:\> Set-SCSQLDeployment -SQLDeployment $SQLDeployment -SQLSysAdminMemberList @("Contoso\SQLAdmins","Contoso\User")
```

The first command gets the SQL Server profile named SQLProfile01, and then stores that object in the $SQLProfile variable.
This command uses the **Get-SCSQLProfile** cmdlet.

The second command gets the SQL Server deployment named SQL Deployment from the SQL profile stored in $SQLProfile, and then stores that object in the $SQLDeployment variable.

The final command modifies the SQL Server administrators for the SQL deployment stored in $SQLDeployment.

## PARAMETERS

### -AgentServiceRunAsAccount
Specifies the Run As account that the SQL Server agent service uses.

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

### -DeploymentRunAsAccount
Specifies the Run As account that this cmdlet uses to modify SQL Server.

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
Specifies the amount of time, in seconds, that the SQL Server deployment waits before it time out.

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

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceName
Specifies the name of a SQL Server Analysis Services (SSAS) database instance.

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
Specifies a media source for the SQL Server deployment to modify.

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

### -MergeSQLAnswerFile
Indicates whether this cmdlet merges the SQL Server configuration file and the guest operating system settings.
The default value is $True.
Virtual Machine Manager Administrator Console uses this parameter.
Do not specify this parameter at the command prompt.

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
Specifies the name of the SQL Server deployment that this cmdlet modifies.

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
Specifies the configuration file for the SQL Server deployment that this cmdlet modifies.

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

### -SQLDeployment
Specifies the SQL Server deployment that this cmdlet modifies.

```yaml
Type: SQLDeployment
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
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

Required: False
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

Required: False
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

[Add-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCSQLDeployment.md)

[Get-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLDeployment.md)

[Remove-SCSQLDeployment](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCSQLDeployment.md)

[Get-SCSQLProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCSQLProfile.md)

