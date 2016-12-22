---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: DC5092DD-488D-4BE4-9343-88B688E0A61F
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCRelationship.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCRelationship.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCRelationship.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCRelationship

## SYNOPSIS

## SYNTAX

### Empty (Default)
```
Get-SCRelationship [[-Source] <ManagementPackClass[]>] [[-Target] <ManagementPackClass[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipDisplayName
```
Get-SCRelationship [-DisplayName] <String[]> [[-Source] <ManagementPackClass[]>]
 [[-Target] <ManagementPackClass[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipId
```
Get-SCRelationship [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCRelationship [-ManagementPack] <ManagementPack[]> [[-Source] <ManagementPackClass[]>]
 [[-Target] <ManagementPackClass[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipName
```
Get-SCRelationship [-Name] <String[]> [[-Source] <ManagementPackClass[]>] [[-Target] <ManagementPackClass[]>]
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

### -ComputerName
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
```yaml
Type: String[]
Parameter Sets: FromRelationshipDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -Id
```yaml
Type: Guid[]
Parameter Sets: FromRelationshipId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ManagementPack
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
```yaml
Type: String[]
Parameter Sets: FromRelationshipName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### -SCSession
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
```yaml
Type: ManagementPackClass[]
Parameter Sets: Empty, FromRelationshipDisplayName, FromManagementPack, FromRelationshipName
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Target
```yaml
Type: ManagementPackClass[]
Parameter Sets: Empty, FromRelationshipDisplayName, FromManagementPack, FromRelationshipName
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

