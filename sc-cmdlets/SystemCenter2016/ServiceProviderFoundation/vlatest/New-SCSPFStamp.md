---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: A1A2F916-1403-4A38-8C05-727D76128982
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFStamp.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFStamp.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFStamp.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCSpfStamp

## SYNOPSIS
Creates a stamp for a server or an instance of a System Center 2016 component.

## SYNTAX

```
New-SCSpfStamp -Name <String> [-DataCenter <DataCenter>] [-Tenants <Tenant[]>] [-Servers <Server[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSPFStamp** cmdlet creates a new stamp, which is a logical scale unit that specifies an instance of a System Center 2016 component running on a server.
As tenants need additional capacity, additional stamps are provided.

## EXAMPLES

### Example 1: Create a stamp
```
PS C:\>New-SCSPFStamp -Name "ContosoStamp"
```

This command creates a stamp.

### Example 2: Create a stamp for a DataCenter object
```
PS C:\>$DataCenterObject = New-Object Microsoft.SystemCenter.Foundation.SPFData.Types.DataCenter
PS C:\> $DataCenterObject.Name = "DataCenter_Contoso"
PS C:\> New-SCSPFStamp -Name "ContosoStamp" -DataCenter DataCenterObject
```

The first command gets a DataCenter object with the New-Object cmdlet with Microsoft.SystemCenter.Foundation.SPFData.Types.DataCenter specified as the value for *TypeName*.

The second command sets the Name property of the DataCenter object to the name of your data center.

The third command creates a stamp.

## PARAMETERS

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

### -DataCenter
Specifies the name of a DataCenter object.

```yaml
Type: DataCenter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies a name for the stamp.

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

### -Servers
Specifies the name of one or more server objects to associate with the new stamp.
To obtain a server, use the Get-SCSPFServer cmdlet.

```yaml
Type: Server[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenants
Specifies the name of one or more tenant objects to associate with the new stamp.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant[]
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

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md)

[Remove-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFStamp.md)

[Set-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md)

