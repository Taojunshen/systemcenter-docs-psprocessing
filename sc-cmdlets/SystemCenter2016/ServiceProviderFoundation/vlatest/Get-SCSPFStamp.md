---
external help file: Microsoft.SystemCenter.Foundation.Cmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 78B47320-21B5-40FC-8452-EA9E6288E9E8
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceProviderFoundation/vlatest/Get-SCSPFStamp.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Get-SCSpfStamp

## SYNOPSIS
Gets one or more stamp objects.

## SYNTAX

### Empty (Default)
```
Get-SCSpfStamp [<CommonParameters>]
```

### FromStampIdAndServerParameterSetName
```
Get-SCSpfStamp -ID <Guid[]> -Server <Server> [<CommonParameters>]
```

### FromStampIdParameterSetName
```
Get-SCSpfStamp -ID <Guid[]> [<CommonParameters>]
```

### FromStampIdAndTenantParameterSetName
```
Get-SCSpfStamp -ID <Guid[]> -Tenant <Tenant> [<CommonParameters>]
```

### FromStampNameAndTenantParameterSetName
```
Get-SCSpfStamp -Name <String[]> -Tenant <Tenant> [<CommonParameters>]
```

### FromStampNameParameterSetName
```
Get-SCSpfStamp -Name <String[]> [<CommonParameters>]
```

### FromStampNameAndServerParameterSetName
```
Get-SCSpfStamp -Name <String[]> -Server <Server> [<CommonParameters>]
```

### FromStampTenantParameterSetName
```
Get-SCSpfStamp -Tenant <Tenant> [<CommonParameters>]
```

### FromStampServerParameterSetName
```
Get-SCSpfStamp -Server <Server> [<CommonParameters>]
```

### FromStampDataCenterParameterSetName
```
Get-SCSpfStamp -DataCenter <DataCenter> [<CommonParameters>]
```

## DESCRIPTION
The **Get-SCSPFStamp** cmdlet gets one or more stamp objects from the Service Provider Foundation service.
To create a stamp, use the New-SCSPFStamp cmdlet.

## EXAMPLES

### Example 1: Get all stamps
```
PS C:\>Get-SCSPFStamp
```

This command lists all stamps.

### Example 2: Get a stamp by ID
```
PS C:\>$Stamp = Get-SCSPFStamp -ID db656655-68ff-4a21-bd1d-0a06bdbc762f
```

This command gets a stamp by its ID.

### Example 3: Get a stamp by name
```
PS C:\>$Stamp = Get-SCSPFStamp -Name "Contoso"
```

This command gets a stamp by its name.

### Example 4: Get the stamps associated with an offer
```
PS C:\>$Offer = Get-SCSPFOffer -Name "Contoso"
PS C:\> $Stamp = Get-SCSPFStamp -Offer $Offer
```

The first command gets an offer.
The second command gets the stamps associated with the offer.

### Example 5: Get the stamp associated with a server
```
PS C:\>$Server = Get-SCSPFServer -Name "ContosoServer07"
PS C:\> $Stamp = Get-SCSPFStamp -Server $Server
```

The first command gets a server.
The second command gets the stamp that is associated with the server.

### Example 6: Get the stamps associated with a tenant
```
PS C:\>$Contoso = Get-SCSPFTenant -Name "Contoso"
PS C:\> $Stamps = Get-SCSPFStamp -Tenant $Contoso
```

The first command gets a tenant.
The second command gets the stamps associated with the tenant.

### Example 7: Get the stamps associated with a data center
```
PS C:\>$DataCenter = New-Object Microsoft.SystemCenter.Foundation.SPFData.Types.DataCenter
PS C:\> $DataCenter.Name = "DataCenter_Contoso"
PS C:\> $Stamps = Get-SCSPFStamp -DataCenter $DataCenter
```

The first command obtains a DataCenter object by using the New-Object cmdlet with Microsoft.SystemCenter.Foundation.SPFData.Types.DataCenter specified for the *$TypeName* parameter.

The second command sets the Name property of the data center object to the name of your data center.

The third command gets the stamps.

## PARAMETERS

### -DataCenter
Specifies the name of a DataCenter object.

```yaml
Type: DataCenter
Parameter Sets: FromStampDataCenterParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ID
Specifies one or more GUIDs for a specific object.

```yaml
Type: Guid[]
Parameter Sets: FromStampIdAndServerParameterSetName, FromStampIdParameterSetName, FromStampIdAndTenantParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of one or more stamps.

```yaml
Type: String[]
Parameter Sets: FromStampNameAndTenantParameterSetName, FromStampNameParameterSetName, FromStampNameAndServerParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies a server for which this cmdlet returns associated stamps.
To obtain a server, use the Get-SCSPFServer cmdlet.

```yaml
Type: Server
Parameter Sets: FromStampIdAndServerParameterSetName, FromStampNameAndServerParameterSetName, FromStampServerParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tenant
Specifies a tenant for which this cmdlet returns associated stamps.
To obtain a tenant, use the Get-SCSPFTenant cmdlet.

```yaml
Type: Tenant
Parameter Sets: FromStampIdAndTenantParameterSetName, FromStampNameAndTenantParameterSetName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Tenant
Parameter Sets: FromStampTenantParameterSetName
Aliases: 

Required: True
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

[New-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/New-SCSPFStamp.md)

[Remove-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Remove-SCSPFStamp.md)

[Set-SCSPFStamp](xref:SystemCenter2016/ServiceProviderFoundation/vlatest/Set-SCSPFStamp.md)

