---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 38c265f6-ffcf-4bbb-a25d-e49307f1f92e
schema: 2.0.0
ms.assetid: BF509EE1-C437-47F9-B4B6-6FC254FD8065
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerProtocol.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerProtocol.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCLoadBalancerProtocol.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCLoadBalancerProtocol

## SYNOPSIS
Creates a load balancer protocol object that is used when you create a load balancer virtual IP.

## SYNTAX

### Base (Default)
```
New-SCLoadBalancerProtocol -Name <String> [<CommonParameters>]
```

### HTTPS
```
New-SCLoadBalancerProtocol -Name <String> [-HTTPSCertificateSubjectName <String>]
 [-HTTPSReencryptConnection <Boolean>] [-TerminateHTTPS <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCLoadBalancerProtocol** cmdlet creates a load balancer protocol object that is used when you create a load balancer virtual IP.

For information about creating a load balancer virtual IP, type `Get-Help New-SCLoadBalancerVIP -Detailed`.

## EXAMPLES

### Example 1: Create an HTTPS load balancer protocol object
```
PS C:\>$LBProtocol = New-SCLoadBalancerProtocol -Name "HTTPS" -HTTPSCertificate "C=US,ST=WA,L=Redmond,O=Contoso,OU=Test,CN=www.contoso.com/emailAddress=contoso@contoso.com" -HTTPSReencryptconnection $True -TerminateHTTPS $True
```

This command creates a load balancer protocol object specifying that HTTPS terminates at the load balancer and that the load balancer re-encrypts the connection to the server.
The command then stores the object in the $LPProtocol variable.

## PARAMETERS

### -HTTPSCertificateSubjectName
Specifies the subject name property of the certificate used to terminate the HTTPS connection at the load balancer. 



Example format: 
`C=US,ST=WA,L=Redmond,O=Contoso,OU=Test,CN=www.contoso.com/emailAddress=contoso@contoso.com`

```yaml
Type: String
Parameter Sets: HTTPS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HTTPSReencryptConnection
Indicates whether a load balancer should re-encrypt traffic to the server after it has terminated an HTTPS connection.

```yaml
Type: Boolean
Parameter Sets: HTTPS
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of a Virtual Machine Manager (VMM) object.

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

### -TerminateHTTPS
Indicates whether HTTPS traffic is terminated at the load balancer.
If set to $True, you must provide a certificate subject name.

```yaml
Type: Boolean
Parameter Sets: HTTPS
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

### LoadBalancerProtocol
This cmdlet returns a **LoadBalancerProtocol** object.

## NOTES

## RELATED LINKS

