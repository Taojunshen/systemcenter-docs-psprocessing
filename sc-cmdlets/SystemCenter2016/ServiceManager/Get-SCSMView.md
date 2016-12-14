---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=225344
schema: 2.0.0
ms.assetid: 6CC3A680-6CD1-4894-B88F-3343C7206DCE
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Get-SCSMView.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Get-SCSMView.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/ServiceManager/Get-SCSMView.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMView

## SYNOPSIS
Retrieves views that are defined in Service Manager.

## SYNTAX

### FromDisplayName (Default)
```
Get-SCSMView [[-DisplayName] <String[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromId
```
Get-SCSMView [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromName
```
Get-SCSMView [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMView** cmdlet retrieves views that are defined in Service Manager.

## EXAMPLES

### Example 1: Display the first three defined views
```
PS C:\>Get-SCSMView | Select-Object -First 3
Name                                                                          Description
----                                                                          -----------
System.WorkItem.Incident.Queue.Tier2.Unassigned.View                          Lists tier 2 open unassigned incidents
AllSoftwareUpdatesView                                                        Lists all software updates
ChangeManagement.Views.ChangeRequestsCancelled                                Lists all canceled change requests
```

This command retrieves all of the views.
The command uses the Select-Object cmdlet to return only the first three views that are defined in Service Manager.

### Example 2: Get the View object
```
PS C:\>Get-SCSMView -Name "System.WorkItem.Incident.Queue.Tier2.Unassigned.View"
Name                                                                          Description
----                                                                          -----------
System.WorkItem.Incident.Queue.Tier2.Unassigned.View                          Lists tier 2 open unassigned incidents
```

This command retrieves the **View** object.

### Example 3: Get the management pack for the View
```
PS C:\>$View = Get-SCSMView -Name "System.WorkItem.Incident.Queue.Tier2.Unassigned.View"
PS C:\> $View.GetManagementPack()
Sealed   Name                                 DisplayName

------   ----                                 -----------

False    ServiceManager.IncidentManagement.Co Service Manager Incident Management

         nfiguration                          Configuration Library
```

The first command retrieves the **View** object, and then stores it in the $View variable.

The second command retrieves the management pack in which the **View** object is defined.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service runs.
The user account that is specified in the *Credential* parameter must have access rights to the specified computer.

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
Specifies the credentials that this cmdlet uses to connect to the server on which the System Center Data Access service runs.
The specified user account must have access rights to that server.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the **View** object to be retrieved.

```yaml
Type: String[]
Parameter Sets: FromDisplayName
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the unique ID of the **View** object to be retrieved.

```yaml
Type: Guid[]
Parameter Sets: FromId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the **View** object to be retrieved.

```yaml
Type: String[]
Parameter Sets: FromName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an object that represents the session to a Service Manager management server.

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

### System.String
You can pipe a name to the *DisplayName* parameter.

### System.Guid
You can pipe a GUID to the *Id* parameter.

## OUTPUTS

### Microsoft.EnterpriseManagement.Configuration.ManagementPackView
This cmdlet returns view objects.

## NOTES

## RELATED LINKS

