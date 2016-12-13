---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 7123a5d8-f693-4b5f-ac54-8d118006202a
schema: 2.0.0
ms.assetid: 655A9353-5415-4A02-A6A9-9EBD69AD4951
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCDiscovery.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/OperationsManager/v1/Get-SCDiscovery.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/OperationsManager/v1/Get-SCDiscovery.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCDiscovery

## SYNOPSIS

## SYNTAX

### Empty (Default)
```
Get-SCDiscovery [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### FromDiscoveryDisplayName
```
Get-SCDiscovery [-DisplayName] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDiscoveryId
```
Get-SCDiscovery [-Id] <Guid[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPack
```
Get-SCDiscovery [-ManagementPack] <ManagementPack[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromDiscoveryName
```
Get-SCDiscovery [-Name] <String[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

### FromManagementPackClass
```
Get-SCDiscovery [-Target] <ManagementPackClass[]> [-SCSession <Connection[]>] [-ComputerName <String[]>]
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

### -DisplayName
```yaml
Type: String[]
Parameter Sets: FromDiscoveryDisplayName
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
Parameter Sets: FromDiscoveryId
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
Parameter Sets: FromDiscoveryName
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

### -Target
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

