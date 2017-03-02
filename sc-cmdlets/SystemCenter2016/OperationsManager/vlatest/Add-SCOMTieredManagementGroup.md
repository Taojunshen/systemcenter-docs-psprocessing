---
external help file: OperationsManager-help.xml
online version: 
schema: 2.0.0
ms.assetid: F9515CE8-BFC0-4619-A1FD-B618A58CBEB1
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTieredManagementGroup.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTieredManagementGroup.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/OperationsManager/vlatest/Add-SCOMTieredManagementGroup.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Add-SCOMTieredManagementGroup

## SYNOPSIS
Adds a tiered management group to a management group.

## SYNTAX

### SimpleAccountTier (Default)
```
Add-SCOMTieredManagementGroup -Name <String> -ServerName <String> -ConnectionCredential <PSCredential>
 [-InactivityTimeout <TimeSpan>] [-SendReceiveTimeout <TimeSpan>] [-CacheMode <CacheMode>]
 [-CacheConfiguration <CacheConfiguration>] [-SCSession <Connection[]>] [-ComputerName <String[]>]
 [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RunAsAccountTier
```
Add-SCOMTieredManagementGroup -Name <String> -ServerName <String> -ConnectionCredential <PSCredential>
 [-InactivityTimeout <TimeSpan>] [-SendReceiveTimeout <TimeSpan>] [-CacheMode <CacheMode>]
 [-CacheConfiguration <CacheConfiguration>] -RunAsAccount <WindowsCredentialSecureData>
 [-AvailableForConnectors] [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-SCOMTieredManagementGroup** cmdlet adds a tiered management group to a management group.
A tiered management group is part of a connected management group that has peer-to-peer connections between its members and that shares member data in a single System Center 2016 - Operations Manager console.

## EXAMPLES

### Example 1: Add a tiered management group
```
PS C:\>Add-SCOMTieredManagementGroup -Name "New Tier" -ServerName "SCOM02.contoso.com" -ConnectionCredential (Get-Credential)
```

This command adds a tiered management group named New Tier to the server named SCOM02.contoso.com.

### Example 2: Add a tiered management group that is available to connectors
```
PS C:\>Add-SCOMTieredManagementGroup -Name "New Tier for Connectors" -ServerName "SCOM02.contoso.com" -ConnectionCredential (Get-Credential) -AvailableForConnectors -RunAsAccount (Get-SCOMRunAsAccount "TierAccount")
```

This command adds a new tiered management group named New Tier for Connectors to the server named SCOM02.contoso.com.
This tiered management group is available to connectors and uses the Run As account named TierAccount.

## PARAMETERS

### -AvailableForConnectors
Indicates that the new tier is available for connectors.

```yaml
Type: SwitchParameter
Parameter Sets: RunAsAccountTier
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheConfiguration
Specifies the cache configuration for the tiered management group.

```yaml
Type: CacheConfiguration
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheMode
Specifies the cache mode for the tiered management group.

```yaml
Type: CacheMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of names of computers.
The cmdlet establishes temporary connections with management groups for these computers.
You can use NetBIOS names, IP addresses, or fully qualified domain names (FQDNs).
To specify the local computer, type the computer name, localhost, or a dot (.).

The computer must run the System Center Data Access service.

If you do not specify this parameter, the default is the computer for the current management group connection.

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

### -ConnectionCredential
Specifies a **PSCredential** object for the management group connection.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the user account under which the management group connection runs.
Specify a **PSCredential** object, such as one that the **Get-Credential** cmdlet returns, for this parameter.
For more information about the **Get-Credential** cmdlet, type `Get-Help Get-Credential`.

If you specify a computer in the *ComputerName* parameter, use an account that has access to that computer.
The default is the current user.

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

### -InactivityTimeout
Specifies the inactivity timeout for the tiered management group.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the new tiered management group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsAccount
Specifies the Run As credential that a management group uses when the tier is available for connectors.

```yaml
Type: WindowsCredentialSecureData
Parameter Sets: RunAsAccountTier
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies an array of **Connection** objects.
To get **Connection** objects, specify the **Get-SCOMManagementGroupConnection** cmdlet.

If you do not specify a value for this parameter, the cmdlet uses the active persistent connection to a management group.
Use the *SCSession* parameter to specify a different persistent connection.
You can create a temporary connection to a management group by using the *ComputerName* and *Credential* parameters.
For more information, type `Get-Help about_OpsMgr_Connections`.

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

### -SendReceiveTimeout
Specifies the send/receive timeout for the tiered management group as a **TimeSpan** object.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name of the SDK server with which to connect in the new tiered management group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCManagementGroupConnection](xref:SystemCenter2016/OperationsManager/vlatest/Get-SCManagementGroupConnection.md)

[New-SCManagementGroupConnection](xref:SystemCenter2016/OperationsManager/vlatest/New-SCManagementGroupConnection.md)

[Set-SCManagementGroupConnection](xref:SystemCenter2016/OperationsManager/vlatest/Set-SCManagementGroupConnection.md)

