---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPhysicalComputerProfile.md
schema: 2.0.0
ms.assetid: B219FAC4-7E2A-4876-B0BF-584D8293A648
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCPhysicalComputerProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCPhysicalComputerProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/Set-SCPhysicalComputerProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# Set-SCPhysicalComputerProfile

## SYNOPSIS
Modifies a physical computer profile object.

## SYNTAX

```
Set-SCPhysicalComputerProfile [[-Name] <String>] [-VirtualHardDisk <VirtualHardDisk>]
 -PhysicalComputerProfile <PhysicalComputerProfile> [-Domain <String>] [-DomainJoinRunAsAccount <RunAsAccount>]
 [-LocalAdministratorCredential <VMMCredential>] [-RemoveAnswerFile] [-RemoveGuiRunOnceCommands]
 [-PhysicalComputerNetworkAdapterProfile <PhysicalComputerNetworkAdapterProfile[]>] [-Description <String>]
 [-Owner <String>] [-DiskConfiguration <String>]
 [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>] [-VMPaths <String>]
 [-FullName <String>] [-GuiRunOnceCommands <String[]>] [-IsGuarded <Boolean>]
 [-CodeIntegrityPolicy <CodeIntegrityPolicy>] [-OrganizationName <String>] [-ProductKey <String>]
 [-TimeZone <Int32>] [-AnswerFile <Script>] [-ComputerAccessRunAsAccount <RunAsAccount>]
 [-Baseline <Baseline[]>] [-JobGroup <Guid>] [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-SCPhysicalComputerProfile** cmdlet modifies a physical computer profile object.

## EXAMPLES

### Example 1: Modify a physical computer profile
```
PS C:\>$PhysicalComputerProfile = Get-SCPhysicalComputerProfile -ID "d1ce0773-4f50-4f12-a244-38a5a35c5326" 
PS C:\> Set-SCPhysicalComputerProfile -PhysicalComputerProfile $PhysicalComputerProfile -RunAsynchronously -Name "Windows Server 2016"
```

The first command stores the physical computer profile that has the specified ID in the $PhysicalComputerProfile variable.

The second command modifies the name of the physical computer profile to be Windows Server 2016.

## PARAMETERS

### -AnswerFile
Specifies a script object stored in the Virtual Machine Manager (VMM) library to use as an answer file.
The name of the answer file script depends on the operating system that you want to install on a virtual machine: 

- Sysprep.inf.
Windows XP, Windows Server 2000, or Windows Server 2003
- Unattend.xml.
Windows Vista, Windows 7, or Windows Server 2008

```yaml
Type: Script
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Baseline
Specifies an array of Baseline objects.

```yaml
Type: Baseline[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BypassVHDConversion
Indicates whether a dynamic VHD attached to a host profile is converted to a fixed type during deployment.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CodeIntegrityPolicy
Specifies a code integrity policy.

```yaml
Type: CodeIntegrityPolicy
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerAccessRunAsAccount
Specifies the computer access Run As account to use to deploy the computer.
This run as account is added to the machine as a local administrator and used to manage the machine.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Description
Specifies a description for the computer profile.

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

### -DiskConfiguration
Specifies the disk and partition configuration for the physical computer that is to be deployed with Windows Hyper-V.

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

### -Domain
Specifies a fully qualified domain name (FQDN) for an Active Directory domain.

Example format: `-Domain "Domain01.Corp.Contoso.com"`

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

### -DomainJoinRunAsAccount
Specifies a Run As account that has permission to join the specified domain.

```yaml
Type: RunAsAccount
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DriverMatchingTag
Specifies the custom tags to match with driver properties during deployment.
When tags are specified, the deployment process matches the tags specified in the host profile with the tags in the drivers in order to download matching drivers and install them in the target image.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FullName
Specifies the name of the person in whose name a virtual machine is registered.

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

### -GuiRunOnceCommands
Specifies an array of commands to add to the **\[GuiRunOnce\]** section of an unattended answer file.
Use single quotation marks around each string enclosed in double quotation marks. 

Example format: 
`-GuiRunOnceCommands '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"', '"C:\APF\APFPostSysPrepCopy.cmd PARAMS1"'`

For information about how Windows PowerShell uses quotation marks, type `Get-Help about_Quoting_Rules`.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsGuarded
Indicates that the host needs to be a Guarded Host.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobGroup
Specifies an identifier for a series of commands that will run as a set just before the final command that includes the same job group identifier runs.

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

### -LocalAdministratorCredential
Specifies the user name and password for the Local Administrator account (or Linux root account in the case of a Linux compatible Guest Operating System profile).

Specifying credentials on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine overrides any existing Administrator password.

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

### -Name
Specifies the name of a VMM object.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationName
Specifies the name of the organization for the person in whose name a virtual machine is registered.

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

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account. 



Example format: `-Owner "Contoso\PattiFuller"`

Example format: `-Owner "PattiFuller@Contoso"`

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

### -PhysicalComputerNetworkAdapterProfile
Specifies an array of physical computer network adapter profile objects.

```yaml
Type: PhysicalComputerNetworkAdapterProfile[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ProductKey
Specifies a product key.
The product key is a 25-digit number that identifies the product license.
A product key can be used to register VMM or an operating system to be installed on a virtual machine or host.

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

### -RemoveAnswerFile
Removes the answer file from the host profile.

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

### -RemoveGuiRunOnceCommands
Removes the GUI Run Once Commands property from the host profile.

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

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see Microsoft Time Zone Index Valueshttp://go.microsoft.com/fwlink/?LinkId=120935  at http://go.microsoft.com/fwlink/?LinkId=120935.
If no time zone is specified, the default time zone used for a virtual machine is the same time zone setting that is on the virtual machine host. 


Example format to specify the GMT Standard Time zone: `-TimeZone 085`

```yaml
Type: Int32
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

### -VMPaths
Specifies a set of default paths (as strings separated by the pipeline operator) on a host where virtual machine files can be stored.

Example format: `-VMPaths "C:\Folder1|C:\Folder2|C:\Folder3"`

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

### -VirtualHardDisk
Specifies a virtual hard disk object.

```yaml
Type: VirtualHardDisk
Parameter Sets: (All)
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

### PhysicalComputerProfile
This cmdlet returns a **PhysicalComputerProfile** object.

## NOTES

## RELATED LINKS

[Get-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Get-SCPhysicalComputerProfile.md)

[New-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/New-SCPhysicalComputerProfile.md)

[Remove-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Remove-SCPhysicalComputerProfile.md)

