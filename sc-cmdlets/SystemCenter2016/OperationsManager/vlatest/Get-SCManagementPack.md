---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 7123a5d8-f693-4b5f-ac54-8d118006202a
schema: 2.0.0
ms.assetid: A345253B-F569-4C25-8494-7BCBFA328472
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCManagementPack.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCManagementPack.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Get-SCManagementPack.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCManagementPack

## SYNOPSIS

## SYNTAX

### Empty (Default)
```
Get-SCManagementPack [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromManagementPackBundle
```
Get-SCManagementPack [-BundleFile] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackFile
```
Get-SCManagementPack [-ManagementPackFile] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackDisplayName
```
Get-SCManagementPack [-DisplayName] <String[]> [-Recurse] [-SCSession <Connection[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackGuid
```
Get-SCManagementPack [-Id] <Guid[]> [-Recurse] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackName
```
Get-SCManagementPack [-Name] <String[]> [-Recurse] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION

## EXAMPLES

### 1:
```
PS C:\>
```

## PARAMETERS

### -BundleFile
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
Parameter Sets: FromManagementPackDisplayName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
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
```yaml
Type: String[]
Parameter Sets: FromManagementPackName
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Recurse
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

## OUTPUTS

## NOTES

## RELATED LINKS

