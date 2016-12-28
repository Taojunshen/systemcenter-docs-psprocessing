---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: CCC68AAD-9A9C-449A-9B50-033918DA1DAA
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClassInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClassInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClassInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSMClassInstance

## SYNOPSIS
Gets class instances.

## SYNTAX

### Empty (Default)
```
Get-SCSMClassInstance [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCSMClassInstance [-Class] <ManagementPackClass[]> [[-Filter] <String>] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMODisplayNameParameterSetName
```
Get-SCSMClassInstance [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMONameParameterSetName
```
Get-SCSMClassInstance [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromGroup
```
Get-SCSMClassInstance [-Group] <EnterpriseManagementObject[]> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromEMOIdParameterSetName
```
Get-SCSMClassInstance [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromCriteria
```
Get-SCSMClassInstance [-Criteria] <EnterpriseManagementObjectCriteria> [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSMClassInstance** cmdlet retrieves class instances.

## EXAMPLES

### Example 1: Get computers by NetBIOS name
```
PS C:\>$MP = Get-SCManagementPack -name "Microsoft.Windows.Library"
PS C:\>$CriteriaFormat = '<Criteria 
>> xmlns="http://Microsoft.EnterpriseManagement.Core.Criteria/"><Reference 
>> Id="Microsoft.Windows.Library" Version="{0}" PublicKeyToken="{1}" 
>> Alias="myMP" 
>>/><Expression><SimpleExpression><ValueExpressionLeft><Property>$Target/Property[Type="myMP!Microsoft.Windows.Computer"]/NetbiosDomainName$</Property></ValueExpressionLeft><Operator>Equal</Operator><ValueExpressionRight><Value>IR2</Value></ValueExpressionRight></SimpleExpression></Expression></Criteria>'
PS C:\>$CriteriaType = "Microsoft.EnterpriseManagement.Common.EnterpriseManagementObjectCriteria"
PS C:\>$criteriaString = $criteriaFormat -f $MP.Version, $MP.KeyToken
PS C:\>$class = Get-SCClass -name "microsoft.windows.computer"
PS C:\>$criteria = new-object $CriteriaType $CriteriaString,$class,$class.ManagementGroup
PS C:\>Get-SCSMClassInstance -criteria $criteria
```

These commands retrieve computers using the criteria of **NetbiosDomainName** equals **WOODGROVE**.
The first commands define the parameters that are then used in the final **Get-SCSMClassInstance** cmdlet.

### Example 2: Get class instances using a filter
```
PS C:\>Get-SCSMClassInstance -class $class -filter 'NetbiosDomainName -eq "WOODGROVE"'
PrincipalName                 ObjectStatus ActiveDirectorySite     NetBiosDomainName
-------------                 ------------ -------------------     -----------------
WIN-752HJBSX24M.woodgrove.com Active       Default-First-Site-Name WOODGROVE
JWT-SCDW.woodgrove.com        Active                               WOODGROVE
```

This command retrieves class instance objects from the Service Manager database using a filter.
Note that the property name in the filter must be the exact name of the property and that it is case sensitive.

### Example 3: Get all computer objects
```
PS C:\>$class = Get-SCSMClass -name microsoft.windows.computer
PS C:\>Get-SCSMClassInstance -class $class|format-table PrincipalName,ObjectStatus,ActiveDirectorySite,NetbiosDomainName
PrincipalName                 ObjectStatus ActiveDirectorySite     NetbiosDomainName
-------------                 ------------ -------------------     -----------------
WIN-752HJBSX24M.woodgrove.com Active       Default-First-Site-Name WOODGROVE
JWT-SCDW.woodgrove.com        Active                               WOODGROVE
```

This commands retrieve all class instance objects of type Computer from the Service Manager database.

## PARAMETERS

### -Class
Specifies the name of one or more classes to retrieve.
You can specify a **ManagementPackClass** object that is returned by the **Get-SCClass** cmdlet.

```yaml
Type: ManagementPackClass[]
Parameter Sets: FromManagementPackClass
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies a computer to establish a connection with.
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
Default value: Current user context
Accept pipeline input: False
Accept wildcard characters: False
```

### -Criteria
Specifies a criteria object that restricts the set of class instances that are returned from the management server.

```yaml
Type: EnterpriseManagementObjectCriteria
Parameter Sets: FromCriteria
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DisplayName
Specifies the display name of the class instance to retrieve.

```yaml
Type: String[]
Parameter Sets: FromEMODisplayNameParameterSetName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Filters the results set.
The syntax of the filter is the \<property\> operator \<value\>, where valid operators are -eq, -ne, -gt, -ge, -lt, -le, -like, and -notlike.
Using a filter is efficient because the filter limits the results that are retrieved from the management server, rather than being applied after the results are returned to PowerShell.

```yaml
Type: String
Parameter Sets: FromManagementPackClass
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Group
Specifies an instance of a group that contains the class instances to retrieve.

```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromGroup
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Id
Specifies the ID of the class instances to retrieve.
This may be a GUID or a string that will be converted to a GUID.

```yaml
Type: Guid[]
Parameter Sets: FromEMOIdParameterSetName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Specifies the name of the class instances to retrieve.

```yaml
Type: String[]
Parameter Sets: FromEMONameParameterSetName
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

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
You can pipe a class to the *Class* parameter of the **Get-SCSMClassInstance** cmdlet.

## OUTPUTS

### EnterpriseManagementObject#<classtype>
This cmdlet generates an **EnterpriseManagementObject#\<classtype\>** object.

## NOTES

## RELATED LINKS

[New-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMClassInstance.md)

[Remove-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMClassInstance.md)

[Update-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMClassInstance.md)

