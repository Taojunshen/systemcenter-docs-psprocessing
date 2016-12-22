---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 796E7137-A063-415A-974D-20401830A574
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualizationManager.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualizationManager.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCVirtualizationManager.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCVirtualizationManager

## SYNOPSIS
Changes the properties of a VMware vCenter Server that is managed by VMM.

## SYNTAX

```
Set-SCVirtualizationManager [-VirtualizationManager] <VirtualizationManager> [-EnableSecureMode <Boolean>]
 [-Credential <VMMCredential>] [-TCPPort <UInt32>] [-Certificate <ClientCertificate>] [-RunAsynchronously]
 [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCVirtualizationManager** cmdlet changes one or more properties of a VMware vCenter Server that is managed by Virtual Machine Manager (VMM).
A vCenter Server manages VMware ESX hosts and VMware-based virtual machines.

Properties that you can change include settings for the TCP port used to connect to the vCenter Server, credentials used to access the vCenter Server, and updating a vCenter Server security certificate.

If a security certificate for a vCenter Server expires or a self-signed certificate is replaced by a certificate from a third-party certification authority (CA), you must update both the vCenter Server and VMM: 



- First, replace the current vCenter certificate with the new  certificate in vCenter.
Refer to the VMware documentation for instructions. 


- Next, update the certificate in VMM by importing the new certificate  into VMM.

For more information about including a VMware VirtualCenter Server as a virtualization managers in a Virtual Machine Manager environment, type `Get-Help Add-SCVirtualizationManager -Detailed`.

## EXAMPLES

### Example 1: Specify new credentials for a virtualization manager
```
PS C:\> $VirtManager = Get-SCVirtualizationManager -ComputerName "VirtMgrServer01.Contoso.com"
PS C:\> $Credential = Get-SCRunAsAccount -Name "RunAsAccount04"
PS C:\> Set-SCVirtualizationManager -VirtualizationManager $VirtManager -Credential $Credential
```

The first command gets the virtualization manager object named VirtMgrServer01 from the VMM database and stores the object in the $VirtManager variable.

The second command gets the Run As account named Host Computer Account 04 and stores it in the $Credential variable.

The last command changes the stored credentials for VirtMgrServer01 that are used when VMM connects to the external service.

## PARAMETERS

### -Certificate
Specifies a security certificate object.

```yaml
Type: ClientCertificate
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type `Get-Help Get-Credential`.

For more information about Run As accounts, type `Get-Help New-SCRunAsAccount`.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSecureMode
Indicates whether VMM communicates with VMware ESX hosts and Citrix XenServer hosts in secure mode.
The default value is $True.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: SecureMode

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -TCPPort
Specifies a numeric value that represents a TCP port.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualizationManager
Specifies a virtualization manager object managed by VMM.

```yaml
Type: VirtualizationManager
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### VirtualizationManager
This cmdlet returns a **VirtualizationManager** object.

## NOTES
* Requires a VMM virtualization manager object, which can be retrieved by using the **Get-SCVirtualizationManager** cmdlet.

## RELATED LINKS

[Add-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Add-SCVirtualizationManager.md)

[Get-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualizationManager.md)

[Read-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCVirtualizationManager.md)

[Remove-SCVirtualizationManager](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCVirtualizationManager.md)

