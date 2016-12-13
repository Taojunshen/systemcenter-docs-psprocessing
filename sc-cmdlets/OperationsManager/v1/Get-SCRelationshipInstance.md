---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: http://go.microsoft.com/fwlink/p/?LinkId=239483
schema: 2.0.0
ms.assetid: 8CBEAB65-6392-4441-B0EF-8A01387D1F07
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCRelationshipInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCRelationshipInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCRelationshipInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCRelationshipInstance

## SYNOPSIS

## SYNTAX

### Empty (Default)
```
Get-SCRelationshipInstance [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromRelationshipInstanceId
```
Get-SCRelationshipInstance [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromRelationshipInstanceSourceTarget
```
Get-SCRelationshipInstance [[-SourceInstance] <EnterpriseManagementObject[]>]
 [[-TargetInstance] <EnterpriseManagementObject[]>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
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

### -Id
```yaml
Type: Guid[]
Parameter Sets: FromRelationshipInstanceId
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
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

### -SourceInstance
```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromRelationshipInstanceSourceTarget
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetInstance
```yaml
Type: EnterpriseManagementObject[]
Parameter Sets: FromRelationshipInstanceSourceTarget
Aliases: 

Required: False
Position: 2
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

