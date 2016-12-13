---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Add-SCLoadBalancer.md
schema: 2.0.0
ms.assetid: 189DC01D-70C3-422F-88B1-A2FF27B3FF14
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLoadBalancer.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLoadBalancer.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Read-SCLoadBalancer.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCLoadBalancer

## SYNOPSIS
Refreshes load balancer information in the VMM console.

## SYNTAX

```
Read-SCLoadBalancer [-VMMServer <ServerConnection>] [-LoadBalancer] <LoadBalancer> [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCLoadBalancer** cmdlet refreshes load balancer information and reflects the updates in the Virtual Machine Manager (VMM) console.

## EXAMPLES

### Example 1: Refresh a load balancer
```
PS C:\>$LoadBalancer = Get-SCLoadBalancer -LoadBalancerAddress "LB01.Contoso.com" 
PS C:\> Read-SCLoadBalancer -LoadBalancer $LoadBalancer
```

The first command gets the load balancer object stored at LB01.Contoso.com and stores the object in the $LoadBalancer variable.

The second command refreshes the load balancer stored in $LoadBalancer.

## PARAMETERS

### -JobVariable
Specifies that job progress is tracked and stored in the variable named by this parameter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancer
Specifies a load balancer object.

```yaml
Type: LoadBalancer
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PROTipID
Specifies the ID of the Performance and Resource Optimization tip (PRO tip) that triggered this action.
This parameter lets you audit PRO tips.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsynchronously
Indicates that the job runs asynchronously so that control returns to the command shell immediately.

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

### -VMMServer
Specifies a VMM server object.

```yaml
Type: ServerConnection
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### LoadBalancer
This cmdlet returns a **LoadBalancer** object.

## NOTES

## RELATED LINKS

[Add-SCLoadBalancer](xref:VirtualMachineManager/v1/Add-SCLoadBalancer.md)

[Get-SCLoadBalancer](xref:VirtualMachineManager/v1/Get-SCLoadBalancer.md)

[Remove-SCLoadBalancer](xref:VirtualMachineManager/v1/Remove-SCLoadBalancer.md)

[Set-SCLoadBalancer](xref:VirtualMachineManager/v1/Set-SCLoadBalancer.md)

[Test-SCLoadBalancer](xref:VirtualMachineManager/v1/Test-SCLoadBalancer.md)

