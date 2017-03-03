---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 7E5FAFF5-1ED2-4C1B-BE7B-852BF006EA44
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMRelationshipInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMRelationshipInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMRelationshipInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSMRelationshipInstance

## SYNOPSIS
Creates an instance of a relationship.

## SYNTAX

### FromRelationshipSourceObjectAndTargetClass
```
New-SCSMRelationshipInstance [-RelationshipClass] <ManagementPackRelationship>
 [-Source] <EnterpriseManagementObject> [-TargetClass] <ManagementPackClass> [-TargetProperty] <Hashtable>
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRelationshipSouceAndTargetObjects
```
New-SCSMRelationshipInstance [-RelationshipClass] <ManagementPackRelationship>
 [-Source] <EnterpriseManagementObject> [-Target] <EnterpriseManagementObject> [-PassThru]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipSourceClassAndTargetObject
```
New-SCSMRelationshipInstance [-RelationshipClass] <ManagementPackRelationship>
 [-Target] <EnterpriseManagementObject> [-SourceClass] <ManagementPackClass> [-SourceProperty] <Hashtable>
 [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRelationshipSourceAndTargetClasses
```
New-SCSMRelationshipInstance [-RelationshipClass] <ManagementPackRelationship>
 [-SourceClass] <ManagementPackClass> [-SourceProperty] <Hashtable> [-TargetClass] <ManagementPackClass>
 [-TargetProperty] <Hashtable> [-PassThru] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMRelationshipInstance** cmdlet creates an instance of a relationship.

## EXAMPLES

### Example 1: Create a relationship instance
```
PS C:\>$Rel = Get-SCRelationship -Name "System.ConfigItemRelatesToConfigItem"
PS C:\>$Mwc = Get-SCClass -Name "Microsoft.Windows.Computer"
PS C:\>$Computers = Get-SCClassInstance -Class $Mwc
PS C:\>New-SCSMRelationshipInstance -RelationshipClass $Rel -Source $Computers[0] -Target $Computers[1]
```

These commands create an instance of a relationship.

## PARAMETERS

### -ComputerName
Specifies the name of the computer on which the System Center Data Access service is running.
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
Specifies the credentials to be used when you are connecting to the server on which the System Center Data Access service is running.
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

### -PassThru
Specifies the output object that represents the new relationship.
This output object can be passed to other cmdlets.

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

### -RelationshipClass
Specifies the class of the relationship to be created.

```yaml
Type: ManagementPackRelationship
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### -Source
Specifies the source of the relationship.

```yaml
Type: EnterpriseManagementObject
Parameter Sets: FromRelationshipSourceObjectAndTargetClass, FromRelationshipSouceAndTargetObjects
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceClass
Specifies the class of the source.

```yaml
Type: ManagementPackClass
Parameter Sets: FromRelationshipSourceClassAndTargetObject, FromRelationshipSourceAndTargetClasses
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceProperty
Specifies the properties and the values of the source class.

```yaml
Type: Hashtable
Parameter Sets: FromRelationshipSourceClassAndTargetObject, FromRelationshipSourceAndTargetClasses
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Specifies the target of the relationship.

```yaml
Type: EnterpriseManagementObject
Parameter Sets: FromRelationshipSouceAndTargetObjects, FromRelationshipSourceClassAndTargetObject
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetClass
Specifies the class of the target of the relationship.

```yaml
Type: ManagementPackClass
Parameter Sets: FromRelationshipSourceObjectAndTargetClass, FromRelationshipSourceAndTargetClasses
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetProperty
Specifies the properties and the values of the target class.

```yaml
Type: Hashtable
Parameter Sets: FromRelationshipSourceObjectAndTargetClass, FromRelationshipSourceAndTargetClasses
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Service Manager Administrator Cmdlets Group 1](xref:SystemCenter2016/ServiceManagerCore/vlatest/ServiceManagerCore.md)

