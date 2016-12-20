---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: ./Disconnect-DPMServer.md
schema: 2.0.0
ms.assetid: 38180443-05A7-481B-A722-91541EDDB664
updated_at: 12/20/2016 10:56 PM
ms.date: 12/20/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Connect-DPMServer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Connect-DPMServer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/39ebc8b68768998222371964f8e90b8160cbfe0a/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Connect-DPMServer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Connect-DPMServer

## SYNOPSIS
Opens a connection to a DPM server.

## SYNTAX

### DPMServerName (Default)
```
Connect-DPMServer [-DPMServerName] <String> [-AsyncOperation <AsyncOperation>] [<CommonParameters>]
```

### DPMServerScope
```
Connect-DPMServer [-DPMServerScope] <DpmServerScope> [-AsyncOperation <AsyncOperation>] [<CommonParameters>]
```

## DESCRIPTION
The **Connect-DPMServer** cmdlet opens a connection to a System Center 2016 - Data Protection Manager (DPM) server.

By default, the cmdlet looks for a DPM server in the current domain.
To connect to a server in another domain, specify the domain name.

## EXAMPLES

### Example 1: Connect to a server
```
PS C:\>Connect-DPMServer -DPMServerName "DPMServer07.Corporate.Contoso.com"
```

This command connects to a DPM server named DPMServer07 in the Corporate.Contoso.com domain.

## PARAMETERS

### -AsyncOperation
Specifies an **AsyncOperation** object.
You can use this parameter to update a GUI that runs in Windows PowerShell, but do not use it in the Windows PowerShell console.

```yaml
Type: AsyncOperation
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of a DPM server for which this cmdlet creates a connection.

```yaml
Type: String
Parameter Sets: DPMServerName
Aliases: ComputerName, CN

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerScope
Specifies a DPM server scope object.
To create a DPM scope object, use the [New-DPMServerScope](./New-DPMServerScope.md) cmdlet.

```yaml
Type: DpmServerScope
Parameter Sets: DPMServerScope
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### DpmServer

## NOTES

## RELATED LINKS

[Disconnect-DPMServer](xref:SystemCenter2016/DataProtectionManager/vlatest/Disconnect-DPMServer.md)

[New-DPMServerScope](xref:SystemCenter2016/DataProtectionManager/vlatest/New-DPMServerScope.md)
