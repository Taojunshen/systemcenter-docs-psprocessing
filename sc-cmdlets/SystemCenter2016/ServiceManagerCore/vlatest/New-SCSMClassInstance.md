---
external help file: Microsoft.EnterpriseManagement.Core.Cmdlets.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 3D2CC7DB-D10D-4138-AE62-9F7A4BB0E570
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMClassInstance.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMClassInstance.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/ServiceManagerCore/vlatest/New-SCSMClassInstance.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# New-SCSMClassInstance

## SYNOPSIS
Adds a class instance to the database.

## SYNTAX

```
New-SCSMClassInstance [-Class] <ManagementPackClass> [-PassThru] [-Property] <Hashtable>
 [-SCSession <Connection[]>] [-ComputerName <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCSMClassInstance** cmdlet adds a class instance to the database.

## EXAMPLES

### Example 1: Create printer class instances
```
PS C:\>0..9 | ForEach-Object {
  New-SCSMClassInstance (Get-SCSMClass â€"Name "Microsoft.Ad.Printer") @{
    UNCName = \\ContosoPrintServer\Printer$_
    ServerName = "ContosoPrintServer"
    PrinterName = "Printer$_"
    Location = "Contoso Headquarters"
    Notes = "Added by PowerShell script." 
  }
}
```

These commands create a set of 10 printer class instances named Printer0 through Printer9.
The location is set to "Contoso Headquarters", and they are all associated with the **ServerName** "ContosoPrintServer".

## PARAMETERS

### -Class
Specifies the class on which the new instance is based.
You can use the **Get-SCClass** cmdlet to obtain the **ManagementPackClass** object that is required for this parameter.

```yaml
Type: ManagementPackClass
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputerName
Specifies a computer with which to establish a connection.
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

### -PassThru
Specifies the output object that represents the new class instance object.
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

### -Property
A hashtable of property-value pairs representing the property values of the new instance.
Each key of the hashtable must be the name of a valid property within the class that is specified in the *Class* parameter and each value must be a valid object that can be stored in the property of its corresponding key.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SCSession
Specifies a connection to a management server.
The default value is the current management group connection.

You can enter a management group connection object that is returned by the `Get-SCManagementGroupConnection` cmdlet.

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

### Microsoft.EnterpriseManagement.Configuration.ManagementPackClass
You can pipe a class to the *Class* parameter of the **New-SCSMClassInstance** cmdlet, for example, the object that is returned by the **Get-SCClass** cmdlet.

## OUTPUTS

###  
This cmdlet does not generate any output.

## NOTES

## RELATED LINKS

[Get-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Get-SCSMClassInstance.md)

[Remove-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Remove-SCSMClassInstance.md)

[Update-SCSMClassInstance](xref:SystemCenter2016/ServiceManagerCore/vlatest/Update-SCSMClassInstance.md)

