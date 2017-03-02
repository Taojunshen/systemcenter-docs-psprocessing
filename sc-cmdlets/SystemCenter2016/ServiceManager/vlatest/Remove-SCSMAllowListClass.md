---
external help file: Microsoft.EnterpriseManagement.ServiceManager.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: C9E8CC32-598D-4684-91C2-DF7A6CC17CD2
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAllowListClass.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAllowListClass.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManager/vlatest/Remove-SCSMAllowListClass.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Remove-SCSMAllowListClass

## SYNOPSIS
Removes the specified classes from the allow list of classes that are used by the Operations Manager CI Connector during synchronization in Service Manager.

## SYNTAX

```
Remove-SCSMAllowListClass [-ClassName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-SCSMAllowListClass** cmdlet removes the specified classes from the allow list of classes that the Operations Manager CI Connector uses during synchronization in Service Manager.
If the class name is not present in the allow list, the cmdlet returns an argument exception.

## EXAMPLES

### Example 1: Remove a class from the allow list
```
PS C:\>Remove-SCSMAllowListClass "System.SoftwareItem"
PS C:\> Get-SCSMAllowList
name                                                        mp
----                                                        --
System.Service                                              System.Library
System.Database                                             System.Library
Microsoft.Windows.ApplicationComponent                      Microsoft.Windows.Library
Microsoft.Windows.ComputerRole                              Microsoft.Windows.Library
System.Computer                                             System.Library
System.OperatingSystem                                      System.Library
Microsoft.Windows.LogicalDevice                             Microsoft.Windows.Library
System.SoftwareInstallation                                 System.Library
System.WebSite                                              System.Library
```

The first command removes the **SoftwareItem** class from the allow list.

The second command retrieves the allow list to verify that the class has been removed.

### Example 2: Attempt to remove an item not in the list
```
PS C:\>Remove-SCSMAllowListClass "System.SoftwareItem"
Remove-SCSMAllowListClass : Class System.SoftwareItem cannot be removed because it is not in the allow list.
At line:1 char:26
+ Remove-SCSMAllowListClass <<<<  "System.SoftwareItem"
    + CategoryInfo          : InvalidData: (System.SoftwareItem:String) [Remove-SCSMAllowListClass], ArgumentException
    + FullyQualifiedErrorId : Invalid allow list XML,Microsoft.EnterpriseManagement.SMCmdlets.RemoveSCSMAllowListClass
```

This command attempts to remove a class that is not in the list.

## PARAMETERS

### -ClassName
Specifies the names of the classes that this cmdlet removes from the allow list of the Operations Manager CI Connector.
Each class name must exist in the allow list, and must correspond to an ID property of a \<ClassType\> management pack element.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None.
You cannot pipe input to this cmdlet.

## OUTPUTS

### None.
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Add-SCSMAllowListClass](xref:SystemCenter2016/ServiceManager/vlatest/Add-SCSMAllowListClass.md)

[Get-SCSMAllowList](xref:SystemCenter2016/ServiceManager/vlatest/Get-SCSMAllowList.md)

[Reset-SCSMAllowList](xref:SystemCenter2016/ServiceManager/vlatest/Reset-SCSMAllowList.md)

