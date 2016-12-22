---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 15ae10d1-5cb5-4f03-aad8-2433553a59ae
schema: 2.0.0
ms.assetid: 3E0E2000-21B4-417B-98F9-0089DAEB0E77
updated_at: 12/21/2016 3:38 PM
ms.date: 12/21/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-CloudVmRole.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-CloudVmRole.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/a51d03bb01e0880c7a55012878712b9f03d07b9c/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Repair-CloudVmRole.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Repair-CloudVmRole

## SYNOPSIS
Repairs a cloud virtual machine role.

## SYNTAX

```
Repair-CloudVmRole [-VmRole] <CloudVmRole> [-VMMServer <ServerConnection>] [-Credential <VMMCredential>]
 [-SkipLastFailedStep] [-RunREST] [-JobVariable <String>] [-OnBehalfOfUser <String>]
 [-OnBehalfOfUserRole <UserRole>] [<CommonParameters>]
```

## DESCRIPTION
The **Repair-CloudVMRole** cmdlet repairs a cloud virtual machine role.

## EXAMPLES


## PARAMETERS

### -Credential
Specifies a credential object or, for some cmdlets, a Run As account object that contains the user name and password of an account that has permission to perform this action.
Or, in the case of **Restart-SCJob**, has permission to complete a restarted task.

For more information about the **PSCredential** object, type: `Get-Help Get-Credential`.

For more information about Run As accounts, type: `Get-Help New-SCRunAsAccount`.

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

### -OnBehalfOfUser
Specifies the name of a user.
This cmdlet sets the on behalf of user as the user that this parameter specifies.

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

### -OnBehalfOfUserRole
Specifies a user role.
This cmdlet sets the on behalf of user role as the user role that this parameter specifies.
To obtain a user role object, use the **Get-SCUserRole** cmdlet.

```yaml
Type: UserRole
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunREST
Indicates that REST APIs are run.

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

### -SkipLastFailedStep
Indicates that the last step that failed will not be rerun when a job is restarted.

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
Specifies a Virtual Machine Manager (VMM) server object.

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

### -VmRole
Specifies a **CloudVMRole** object.

```yaml
Type: CloudVmRole
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

## NOTES

## RELATED LINKS

