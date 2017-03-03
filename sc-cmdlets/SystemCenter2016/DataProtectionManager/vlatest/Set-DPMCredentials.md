---
external help file: ObjectModelCmdlet.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 4E8D72F4-1442-43DD-9E56-4F9AD90367E7
updated_at: 12/22/2016 5:54 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCredentials.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCredentials.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/17c3a51bd892aad46c731d9f381f0704b4815004/systemcenter-cmdlets/SystemCenter2016/DataProtectionManager/vlatest/Set-DPMCredentials.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: True
ms.service: system-center
---

# Set-DPMCredentials

## SYNOPSIS
Configures authentication for computers in untrusted domains.

## SYNTAX

```
Set-DPMCredentials [[-DPMServerName] <String>] [-Type] <AuthenticationType> [-Action] <Action>
 [-OutputFilePath] <String> [[-Thumbprint] <String>] [[-AuthCAThumbprint] <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-DPMCredentials** cmdlet configures certificate-based authentication for computers for System Center 2016 - Data Protection Manager (DPM) to protect that are in untrusted domains.

## EXAMPLES

### Example 1: Configure authentication with a new certificate
```
PS C:\>Set-DPMCredentials -DPMServerName "Dpmserver.Contoso.com" -Type Certificate -Action Configure -OutputFilePath "C:\CertMetaData\" -Thumbprint "cf822d9ba1c801ef40d4b31de0cfcb200a8a2496"
```

This command configures authentication for the DPM server named Dpmserver.Contoso.com.
The command creates a file in the folder C:\CertMetaData\ with the name CertificateConfiguration_\<DPM-server-FQDN\>.bin.

### Example 2: Configure authentication with a regenerated configuration file
```
PS C:\>Set-DPMCredentials -DPMServerName "Dpmserver.Contoso.com" -Type Certificate -OutputFilePath "C:\CertMetaData\" -Action Regenerate
```

This cmdlet configures the DPM server named Dpmserver.Contoso.com by regenerating the lost configuration file in the folder C:\CertMetaData\.

## PARAMETERS

### -Action
Specifies the action to perform.

The acceptable values for this parameter are:

- Configure.
Use a new certificate.
- Regenerate.
Regenerate the output metadata file.

```yaml
Type: Action
Parameter Sets: (All)
Aliases: 
Accepted values: Configure, Regenerate

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthCAThumbprint
Specifies the thumbprint of a certifying authority in the trust chain of the certificate.
If you do not specify this parameter, DPM uses the value Root.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DPMServerName
Specifies the name of the DPM server on which this cmdlet acts.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFilePath
Specifies the location of the output file.
Specify this path by using the **Set-DPMServer** tool to complete configuration for protection agents on the DPM server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Specifies the thumbprint to use when you search for the certificate.
You must specify this parameter if you specify Configure as the value for the *Action* parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Specifies the type of credential that this cmdlet adds.
This parameter accepts only the value Certificate.

```yaml
Type: AuthenticationType
Parameter Sets: (All)
Aliases: 
Accepted values: Certificate

Required: True
Position: 2
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

[Data Protection Manager Cmdlets](xref:SystemCenter2016/DataProtectionManager/vlatest/DataProtectionManager.md)

