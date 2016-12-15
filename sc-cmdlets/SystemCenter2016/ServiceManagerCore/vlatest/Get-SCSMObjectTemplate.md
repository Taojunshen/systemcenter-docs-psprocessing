---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225405
schema: 2.0.0
ms.assetid: 4BA91FB3-5B6E-42F6-BC7C-CC5E59B4F49F
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMObjectTemplate.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMObjectTemplate.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMObjectTemplate.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMObjectTemplate

## SYNOPSIS
Gets an object template.

## SYNTAX

### Empty (Default)
```
Get-SCSMObjectTemplate [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromClassDisplayName
```
Get-SCSMObjectTemplate [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassGuids
```
Get-SCSMObjectTemplate [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCSMObjectTemplate [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromClassName
```
Get-SCSMObjectTemplate [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMObjectTemplate** cmdlet retrieves an object template that is defined in Service Manager.

## EXAMPLES

### Example 1: Get all object templates
```
PS C:\>Get-SCSMObjectTemplate
Name                                                                     Description
----                                                                     -----------
PortalIncidentTemplate                                                   Template applied to incidents created via the portal
AssignedToUserNotificationTemplate                                       Use for notifications sent to the user who is assigned the incident
StandardChangeRequest                                                    Standard Change Requests are pre-approved and used for low-risk pre-tested cha...
DataProvider.Microsoft.EnterpriseManagement.ServiceManager.Connector.AD  Linking Framework Active Directory Data Provider class
DataConsumer.Microsoft.EnterpriseManagement.ServiceManager.Connector.Sms Linking Framework Configuration Manager Data Consumer class
AffectedUserNotificationTemplate                                         Use for notifications sent to end users
NetworkingIssueIncidentTemplate                                          Use for incidents that are for networking problems
ChangeRequestAssignedToUserNotificationTemplate                          Use for notifications sent to the user who is assigned the change request
OpsMgr.CIList.Template                                                   This template sets the base classes that control which configuration items are...
DefaultParallelActivityTemplate                                          Default Parallel Activity
SecurityReleaseChangeRequest                                             Use Security Release template for security patch scenario. It includes typical...
EscalationNotificationTemplate                                           Use for notifications sent when an incident is escalated
DataProvider.Microsoft.EnterpriseManagement.ServiceManager.Connector.Sms Linking Framework Configuration Manager Data Provider class
MinorChangeRequest                                                       Minor Change Requests can be approved by change manager. Use them for low-risk...
DefaultIncidentTemplate                                                  Use when you want to open an incident for which you do not have a specific tem...
DefaultDependentActivityTemplate                                         Default Dependent Activity
EmergencyChangeRequest                                                   Emergency Change Requests are used for urgent changes which should be implemen...
DataConsumer.Microsoft.EnterpriseManagement.ServiceManager.Connector.AD  Linking Framework Active Directory Data Consumer class
SoftwareIssueIncidentTemplate                                            Use for incidents that are for software problems
HighPriorityIncidentTemplate                                             Use for incidents that have high impact and high urgency
MajorChangeRequest                                                       Major Change Requests should be screened by Change Manager. Change Advisory Bo...
DefaultReviewActivityTemplate                                            Default Review Activity
HardwareIssueIncidentTemplate                                            Use for incidents that are for hardware problems
DefaultSequentialActivityTemplate                                        Default Sequential Activity
PrintingIssueIncidentTemplate                                            Use for incidents that are for printing problems
DefaultManualActivityTemplate                                            Default Manual Activity
Microsoft.SystemCenter.WorkItem.SCOMIncident.Template                    System Center Operations Manager incident template
DefaultReleaseRecord                                                     Default Release Record
```

This command retrieves all object templates that are defined in Service Manager.

### Example 2: Get object templates by name
```
PS C:\>Get-SCSMObjectTemplate â€"name "StandardChangeRequest"
StandardChangeRequest


Name                  Description
----                  -----------
StandardChangeRequest Standard Change Requests are pre-approved and used for low-risk pre-tested change operations.
```

This command retrieves the object template with the name StandardChangeRequest.

## PARAMETERS

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
Default value: None
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
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the object template to retrieve.

```yaml
Type: String[]
Parameter Sets: FromClassDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the ID of the object template to retrieve.

```yaml
Type: Guid[]
Parameter Sets: FromClassGuids
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
Specifies the management pack containing the object templates to retrieve.
You can enter a ManagementPack object that is returned by the Get-SCSMManagementPack cmdlet.

```yaml
Type: ManagementPack[]
Parameter Sets: FromManagementPack
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the Name of the object template to retrieve.

```yaml
Type: String[]
Parameter Sets: FromClassName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the Get-SCSMManagementGroupConnection cmdlet.

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
You can pipe a GUID of an object template to the *Id* parameter of the **Get-SCSMObjectTemplate** cmdlet.

### Microsoft.EnterpriseManagement.Configuration.ManagementPack
You can pipe a management pack object to the *ManagementPack* parameter of the **Get-SCSMObjectTemplate** cmdlet.

### System.String
You can pipe a name of a template to the **Name** parameter of the **Get-SCSMObjectTemplate** cmdlet.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackObjectTemplate
This cmdlet retrieves all template objects.

## NOTES

## RELATED LINKS

[Service Manager Administrator Cmdlets Group 1](xref:SystemCenter2016/ServiceManagerCore/vlatest/ServiceManagerCore.md)

