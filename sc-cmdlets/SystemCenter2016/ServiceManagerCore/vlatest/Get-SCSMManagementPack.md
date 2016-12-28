---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 395872CF-FF24-4684-A8C8-848834B5E5DE
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMManagementPack

## SYNOPSIS
Gets management packs.

## SYNTAX

### Empty (Default)
```
Get-SCSMManagementPack [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPackBundle
```
Get-SCSMManagementPack [-BundleFile] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackFile
```
Get-SCSMManagementPack [-ManagementPackFile] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackDisplayName
```
Get-SCSMManagementPack [-DisplayName] <String[]> [-Recurse] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackGuid
```
Get-SCSMManagementPack [-Id] <Guid[]> [-Recurse] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackName
```
Get-SCSMManagementPack [-Name] <String[]> [-Recurse] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMManagementPack** cmdlet retrieves management packs that have been imported into a management group, exist in management pack files (.mp, .xml), or reside within a management pack bundle (.mpb) file.

## EXAMPLES

### Example 1: Get all imported management packs
```
PS C:\>Get-SCSMManagementPack
Sealed Name                                                            DisplayName
------ ----                                                            -----------
True Microsoft.SystemCenter.InstanceGroup.Library                    Instance Group Library
True Microsoft.Windows.Peripheral.Library                            Windows Peripheral Library
True ServiceManager.ActivityManagement.Library
True System.Software.Library                                         System Software Library
True Microsoft.SystemCenter.Deployment.Library
True ServiceManager.KnowledgeManagement.Library
True Microsoft.EnterpriseManagement.ServiceManager.UI.Administration ServiceManager Administration ManagementPack
False ServiceManager.LinkingFramework.Configuration
True ServiceManager.LinkingFramework.Library
True System.Snmp.Library                                             SNMP Library
True ServiceManager.Core.Library                                     Service Manager Core Library
True Microsoft.EnterpriseManagement.ServiceManager.UI.Console        Service Manager Console ManagementPack
True System.ApplicationLog.Library                                   Application Log Library
True Microsoft.EnterpriseManagement.ServiceManager.UI.Authoring      Service Manager Authoring ManagementPack
True Microsoft.SystemCenter.Library                                  System Center Core Library
False Microsoft.EnterpriseManagement.ServiceManager.Default
True Microsoft.SystemCenter.WorkItemGroup.Library                    Instance Group Library
True System.Library                                                  System Library
True Microsoft.Windows.Library                                       Windows Core Library
True Microsoft.SystemCenter.ConfigurationManager                     Microsoft SystemCenter ConfigurationManager Library
True Microsoft.EnterpriseManagement.ServiceManager.Connector.Sms
False ServiceManager.ChangeManagement.Configuration                   ServiceManager ChangeManagement Configuration
True System.Health.Library                                           Health Library
True Microsoft.SystemCenter.WorkflowFoundation.Library               System Center Workflow Foundation Library
True Microsoft.SystemCenter.Report.Library
True ServiceManager.Datawarehouse.Library
True Microsoft.EnterpriseManagement.ServiceManager.Connector.AD
True ServiceManager.ConfigurationManagement.Library
False ServiceManager.ActivityManagement.Configuration
True System.Notifications.Library                                    System Notification Library
True ServiceManager.IncidentManagement.Library                       Incident Management Library
True Microsoft.SystemCenter.Subscriptions
True ServiceManager.ChangeManagement.Library
True System.Performance.Library                                      Performance Library
False ServiceManager.IncidentManagement.Configuration                 Incident Management Configuration
```

This command retrieves all imported management packs.

### Example 2: Get an individual management pack
```
PS C:\>Get-SCSMManagementPack -Name "System.Library"
Sealed Name           DisplayName
------ ----           -----------
True System.Library System Library
```

This command retrieves the System.Library management pack.

## PARAMETERS

### -BundleFile
Specifies the names of the management pack bundle files (.mpb) from which to retrieve management packs.

```yaml
Type: String[]
Parameter Sets: FromManagementPackBundle
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies a computer with which to establish a connection.
The computer must be running the System Center Data Access service.
The default value is the computer for the current management group connection.

Valid formats include a NetBIOS name, an IP address, or a fully qualified domain name (FQDN).
To specify the local computer, type the computer name, "localhost", or a dot (.).

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Localhost
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user account under which the management group connection will run.
The account must have access to the server that is specified in the *ComputerName* parameter, if the server is specified.
The default value is the current user.

You can enter a **PSCredential** object that is returned by the **Get-Credential** cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: The user account of the current context
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the management packs to retrieve.
This parameter is interpreted as a regular expression.

```yaml
Type: String[]
Parameter Sets: FromManagementPackDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the management packs to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromManagementPackGuid
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPackFile
Specifies the file name (.xml or .mp) of the management packs to retrieve.

```yaml
Type: String[]
Parameter Sets: FromManagementPackFile
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the names of the management packs to retrieve.
This parameter is interpreted as a regular expression.

```yaml
Type: String[]
Parameter Sets: FromManagementPackName
Aliases: 

Required: True
Position: 1
Default value: .*
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Recurse
Indicates that the specified management pack, and all management packs that depend on it, are retrieved.

```yaml
Type: SwitchParameter
Parameter Sets: FromManagementPackDisplayName, FromManagementPackGuid, FromManagementPackName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the **Get-SCManagementGroupConnection** cmdlet.

```yaml
Type: Connection[]
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

### System.Guid
You can pipe the GUID of a management pack to the *Id* parameter of the **Get-SCSMManagementPack** cmdlet.

### System.String
You can pipe the name of a management pack to the *Name* parameter of the **Get-SCSMManagementPack** cmdlet.

## OUTPUTS

### Microsoft.EnterpiseManagement.Configuration.ManagementPack
The management pack object contains the management pack and its properties.

## NOTES

## RELATED LINKS

[Import-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Import-SCSMManagementPack.md)

[Export-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Export-SCSMManagementPack.md)

[New-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPack.md)

[Protect-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Protect-SCSMManagementPack.md)

[Test-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Test-SCSMManagementPack.md)

[New-SCSMManagementPackBundle](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMManagementPackBundle.md)

[Remove-SCSMManagementPack](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMManagementPack.md)

