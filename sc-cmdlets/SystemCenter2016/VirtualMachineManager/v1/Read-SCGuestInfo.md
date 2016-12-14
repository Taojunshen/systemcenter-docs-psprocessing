---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: C44CA1EF-CFAD-4F6F-BEC6-3EB6598D6C43
updated_at: 12/14/2016 11:37 PM
ms.date: 12/14/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCGuestInfo.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCGuestInfo.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ddd0fefc9adaabb9394eb6c21b33370913d1830d/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/v1/Read-SCGuestInfo.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Read-SCGuestInfo

## SYNOPSIS
Retrieves the value associated with a key in a guest operating system.

## SYNTAX

### MultipleKvpKeys (Default)
```
Read-SCGuestInfo [-VM] <VM> -KvpMap <Hashtable> [<CommonParameters>]
```

### SingleKvpKey
```
Read-SCGuestInfo [-VM] <VM> [-Key] <String> [<CommonParameters>]
```

## DESCRIPTION
The **Read-SCGuestInfo** cmdlet retrieves the value associated with a key (key/value pair) in a guest operating system.

## EXAMPLES

### Example 1: Get the IntegrationServicesVersion value for a specified key for a virtual machine
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> Read-SCGuestInfo -VM $VM -Key "FullyQualifiedDomainName"
```

The first command gets the virtual machine object named $VM01 and stores the object in the $VM variable.

The second command returns the IntegrationServicesVersion key/value pair for virtual machine VM01.

### Example 2: Get the IntegrationServicesVersion value for a specified key for a virtual machine by using the pipeline operator
```
PS C:\>Get-SCVirtualMachine -Name "VM01" | Read-SCGuestInfo -Key IntegrationServicesVersion
```

This command returns the IntegrationServicesVersion key/value pair for virtual machine VM01.

### Example 3: Get multiple KVP values based on specified keys for a virtual machine
```
PS C:\>$ValuesMap = @{}
PS C:\> $ValuesMap.Add("NetworkAddressIPv4", $Null)
PS C:\> $ValuesMap.Add("IntegrationServicesVersion", $Null)
PS C:\> $VM = Get-SCVirtualMachine "VM02" 
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap
```

The first command creates an array named $ValuesMap.

The second and third commands add values to the $ValuesMap array.

The fourth command gets the virtual machine object named VM02 and stores the object in the $VM variable.

The last command returns the IntegrationServicesVersion and NetworkAddressIPv4 key/value pairs for virtual machine VM02.

### Example 4: Read multiple data types through a hashtable
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM03"
PS C:\> $ValuesMap = @{}
PS C:\> $ValuesMap.Add("NetworkAddressIPv4", $Null)
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> $ValuesMap.Add("NetworkAddressIPv6", $Null)
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> $ValuesMap2 = @{"NetworkAddressIPv4" = $Null; "FullyQualifiedDomainName" = $Null}
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap2
```

The first command gets the virtual machine object named VM03 and stores the object in the $VM variable.

The second command creates an array named $ValuesMap.

The third command adds NetworkAddressIPv4 to the $ValuesMap array.

The fourth command gets the NetworkAddressIPv4 key/value pair for VM03.

The fifth command adds NetworkAddressIPv6 to the $ValuesMap array.

The sixth command gets the NetworkAddressIPv6 key/value pair for VM03.

The seventh command creates an array named $ValuesMap2 which contains NetworkAddressIPv4 and FullyQualifiedDomainName.

The last command returns the key/value pairs for NetworkAddressIPv4 and FullyQualifiedDomainName for VM03.

### Example 5: Read keys that do not exist
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $KeysDoNotExist = @{"o1ff1" = $Null; "o1ff2" = $Null; "o1ff3" = $Null ; "o1ff4" = $Null }
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $KeysDoNotExist 
PS C:\> $KeysDoNotExist = @{"off4" = $Null; "o1ff2" = $Null; "o1ff3" = $Null ; "o1ff4" = $Null }
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $KeysDoNotExist 
PS C:\> $KeysDoNotExist = @{"o1ff1" = $Null; "o1ff2" = $Null; "off4" = $Null ; "o1ff4" = $Null }
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $KeysDoNotExist
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second, fourth, and sixth commands each create a set of keys that are null and stores the set in the $KeysDoNotExist variable.

The third, fifth, and seventh commands read the KVPMap in $KeysDoNotExist and displays the results.

## PARAMETERS

### -Key
Specifies the key in a key/value pair.

```yaml
Type: String
Parameter Sets: SingleKvpKey
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KvpMap
Specifies a hash table of key/value pairs corresponding to the values exposed by Hyper-V.

```yaml
Type: Hashtable
Parameter Sets: MultipleKvpKeys
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies a virtual machine object.

```yaml
Type: VM
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

### String
This cmdlet returns a **String** object.

## NOTES

## RELATED LINKS

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/v1/Get-SCVirtualMachine.md)

[Set-SCGuestInfo](xref:SystemCenter2016/VirtualMachineManager/v1/Set-SCGuestInfo.md)

