---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 35D67CB4-7CF8-4B28-9E81-CE6719D52481
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAllowList.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAllowList.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Get-SCSMAllowList.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Get-SCSMAllowList

## SYNOPSIS
Retrieves the allow list of classes that is used during synchronization.

## SYNTAX

```
Get-SCSMAllowList [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMAllowList** cmdlet retrieves the allow list of classes that the Service Manager Operations Manager CI Connector uses during synchronization.
The connector imports only the instances of the class types that this allow list includes.

## EXAMPLES

### Example 1: Get the allow list for the local computer
```
PS C:\>Get-SCSMAllowList
Name                                                                MP
----                                                                --
System.Service                                                      System.Library
System.Database                                                     System.Library
Microsoft.Windows.ApplicationComponent                              Microsoft.Windows.Library
Microsoft.Windows.ComputerRole                                      Microsoft.Windows.Library
System.Computer                                                     System.Library
System.OperatingSystem                                              System.Library
Microsoft.Windows.LogicalDevice                                     Microsoft.Windows.Library
System.SoftwareInstallation                                         System.Library
System.WebSite                                                      System.Library
```

This command retrieves the allow list on the local computer by using the credentials of the current user.

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
Default value: Localhost
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

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### System.Xml.XmlElement
This cmdlet returns a list of pairs that each contain the class name and management pack for each class type in the allow list.

## NOTES

## RELATED LINKS

[Add-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/vlatest/Add-SCSMAllowListClass.md)

[Remove-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAllowListClass.md)

[Reset-SCSMAllowList](xref:SystemCenter2016/ServiceManager/vlatest/Reset-SCSMAllowList.md)

