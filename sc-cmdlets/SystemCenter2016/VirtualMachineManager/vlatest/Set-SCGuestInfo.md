---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCVirtualMachine.md
schema: 2.0.0
ms.assetid: D6ECDC8C-DF79-43BC-8B59-994F48512DA7
updated_at: 12/15/2016 4:04 AM
ms.date: 12/15/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestInfo.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestInfo.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/7df4508c7b907a214e6a8eca76037b06065ef078/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestInfo.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCGuestInfo

## SYNOPSIS
Sets the value associated with a key for a key/value pair in a guest operating system.

## SYNTAX

### MultipleKvpKeys
```
Set-SCGuestInfo [-VM] <VM> -KvpMap <Hashtable> [<CommonParameters>]
```

### SingleKvpKey
```
Set-SCGuestInfo [-VM] <VM> [-Key] <String> [[-Value] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCGuestInfo** cmdlet sets the value associated with a key for a key/value pair in a guest operating system.

## EXAMPLES

### Example 1: Set a single key/value pair
```
PS C:\>$VM = Get-SCVirtualMachine "VM01" 
PS C:\> Set-SCGuestInfo -VM $VM -Key Key -Value Value
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command sets a key/value pair for VM01.

### Example 2: Set a key to a value for a key/value pair
```
PS C:\> Get-SCVirtualMachine -Name "VM01" | Set-SCGuestInfo -Key Microsoft.Lab.Isolation.ServerVersion -Value 1.0.1101
```

This command sets the key to Microsoft.Lab.Isolation.ServerVersion and the value to 1.0.1101 for the virtual machine named VM01.
If the key does not exist, it will be created with the specified value.
If the key already exists, its value will be overwritten using the value specified in this command.

You can use the Read-SCGuestInfo cmdlet to provide the key and return its corresponding value.

### Example 3: Set multiple key/value pairs
```
PS C:\>$VM = Get-SCVirtualMachine -Name "Win2k8R2"
PS C:\> $ValuesMap  = @{"Key1" = "avalue1"; "Key2IsEmptyString" = "" ; "Key3" = "value3"}
PS C:\> Set-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap | Select KvpMap
```

The first command gets the virtual machine object named Win2k8R2 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap that contains the corresponding keys and values for the key/value pairs.
Values can be set to a string, an empty string, or $Null.
Setting a value to $Null deletes the key.

The third command sets the key/value pairs for the virtual machine named Win2k8R2.

The last command reads back the key/value pairs for the virtual machine named Win2k8R2.

### Example 4: Modify a set of values for a set of key/value pairs
```
PS C:\>$VM = Get-SCVirtualMachine -Name "Win2k8R2"
PS C:\> $ValuesMap  = @{"Key1" = "avalue1"; "Key2IsEmptyString" = "" ; "Key3" = "value3"}
PS C:\> Set-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap | Select KvpMap
PS C:\> $ValuesMap  = @{"Key2IsEmptyString" = "KeyIsNoLongerEmpty"}
PS C:\> Set-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> $ValuesMap  = @{"Key1" = $Null; "Key2IsEmptyString" = $Null; "Key3" = $Null}
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap | Select KvpMap
```

The first command gets the virtual machine object named Win2k8R2 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap that contains the corresponding keys and values for the key/value pairs.
Values can be set to a string, an empty string, or $Null.
Setting a value to $Null deletes the key.

The third command sets the key/value pairs for the virtual machine named Win2k8R2.

The fourth command reads back the key/value pairs for the virtual machine named Win2k8R2.

The fifth command creates a new hashtable where a specific key is changed to a different value.

The sixth command sets the modified value for the specified key in the hashtable.

The last two commands read back the key/value pairs for the virtual machine named Win2k8R2, including the modifiied value for the key Key2IsEmptyString.

### Example 5: Delete a key/value pair using two methods
```
PS C:\>$VM = Get-SCVirtualMachine -Name "Win2k8R2"
PS C:\> $ValuesMap  = @{"Key1" = "avalue1"; "Key2" = "avalue2"}
PS C:\> Set-SCGuestInfo -VM $VM -KvpMap $ValuesMap
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap | Select KvpMap
PS C:\> Set-SCGuestInfo -VM $VM -Key Key1 
PS C:\> $KvpsToDelete  = @{"Key2" = $Null}
PS C:\> Set-SCGuestInfo -VM $VM -KvpMap $KvpsToDelete  
PS C:\> Read-SCGuestInfo -VM $VM -KvpMap $ValuesMap | Select KvpMap
```

The first command gets the virtual machine object named Win2k8R2 and stores the object in the $VM variable.

The next three commands create two keys and their values and return them to the console for virtual machine Win2k8R2.

The fifth command deletes the key/value pair Key1 by calling **Set-SCGuestInfo** without specifying the value parameter.

The sixth and seventh commands create a new Hashtable with Null as the value for key Key2.
Then, key Key2 is deleted by calling the **Set-SCGuestInfo** cmdlet.

The last command shows that both keys that were initially created are now deleted via two separate methods.

### Example 6: Set multiple values where one value is empty
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $ValuesMap3 = @{"VSLM1" = "value1"; "VLSM2" = "value2" ; "VLSM3" = "value3" ; "VLDM4" = ""}
PS C:\> Set-SCGuestInfo -VM $VM -KVPMap $ValuesMap3
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $ValuesMap3 | Select KVPMap
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap3 that contains the corresponding keys and values for the key/value pairs.
Values can be set to a string, an empty string, or $Null.
Setting a value to $Null deletes the key.

The third command sets the values for the specified keys in the hashtable.

The last command reads back the key/value pairs for the virtual machine named VM01.

### Example 7: Delete one value and set another value to empty
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $ValuesMap4 = @{"VLSM2" = $Null; "VSLM1" = "" }
PS C:\> Set-SCGuestInfo -VM $VM -KVPMap $ValuesMap4
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $ValuesMap4 | Select KVPMap
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap4 that contains the corresponding keys and values for the key/value pairs.
Values can be set to a string, an empty string, or $Null.
Setting a value to $Null deletes the key.

The third command sets the values for the specified keys in the hashtable.

The fourth command deletes key VLSM2 and sets key VSLM1 to empty by calling the **Set-SCGuestInfo** command.

The last command reads back the key/value pairs for the virtual machine named VM01.

### Example 8: Set one value and delete another value
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $ValuesMap5 = @{"VSLM1" = "data again"; "VLSM3" = $Null }
PS C:\> Set-SCGuestInfo -VM $VM -KVPMap $ValuesMap5
PS C:\> Read-SCGuestInfo -VM $VM -KVPMap $ValuesMap5 | Select KVPMap
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap5 that contains the corresponding keys and values for the key/value pairs.
Values can be set to a string, an empty string, or $Null.
Setting a value to $Null deletes the key.

The fourth command sets key VSLM1 to "data again" and deletes key VLSM3 by calling the **Set-SCGuestInfo** command.

The last command reads back the key/value pairs for the virtual machine named VM01.

### Example 9: Ignore the deletion of keys that do not exist
```
PS C:\>$VM = Get-SCVirtualMachine -Name "VM01"
PS C:\> $KeysDoNotExist  = @{"o1ff1" = $Null; "o1ff2" = $Null; "o1ff3" = $Null ; "o1ff4" = $Null }
PS C:\> Set-SCGuestInfo -VM $VM -KVPMap $KeysDoNotExist 
PS C:\> Set-SCGuestInfo -VM $VM -Key "o1ff1"
```

The first command gets the virtual machine object named VM01 and stores the object in the $VM variable.

The second command creates a hashtable named $ValuesMap5 that contains the corresponding keys and values for the key/value pairs.
Setting a value to $Null deletes the key.

The third command sets the values to $Null for the specified keys in the hashtable.

The last command deletes all keys in the hashtable except for key o1ff1 by calling the **Set-SCGuestInfo** cmdlet.

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

### -Value
Specifies a string used to attribute an object or property.

```yaml
Type: String
Parameter Sets: SingleKvpKey
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
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

[Get-SCVirtualMachine](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCVirtualMachine.md)

[Read-SCGuestInfo](xref:SystemCenter2016/VirtualMachineManager/vlatest/Read-SCGuestInfo.md)

