---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCPhysicalComputerProfile.md
schema: 2.0.0
ms.assetid: A9068935-7075-40A5-89A6-D001B4B2D84D
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCPhysicalComputerProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCPhysicalComputerProfile

## SYNOPSIS
Creates a profile that is used to deploy an operating system to a computer.

## SYNTAX

### CreateNewHostProfileData
```
New-SCPhysicalComputerProfile [-Name] <String> -VirtualHardDisk <VirtualHardDisk> -Domain <String>
 -DomainJoinRunAsAccount <RunAsAccount> -LocalAdministratorCredential <VMMCredential> [-UseAsVMHost]
 -PhysicalComputerNetworkAdapterProfile <PhysicalComputerNetworkAdapterProfile[]>
 [-ComputerAccessRunAsAccount <RunAsAccount>] [-DiskConfiguration <String>]
 [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>] [-VMPaths <String>]
 [-FullName <String>] [-IsGuarded <Boolean>] [-CodeIntegrityPolicy <CodeIntegrityPolicy>]
 [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>] [-TimeZone <Int32>]
 [-Baseline <Baseline[]>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### CreateNewWorkgroupHostProfileData
```
New-SCPhysicalComputerProfile [-Name] <String> -VirtualHardDisk <VirtualHardDisk> [-JoinWorkgroup]
 -LocalAdministratorCredential <VMMCredential> [-UseAsVMHost]
 -PhysicalComputerNetworkAdapterProfile <PhysicalComputerNetworkAdapterProfile[]>
 [-ComputerAccessRunAsAccount <RunAsAccount>] [-DiskConfiguration <String>]
 [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>] [-VMPaths <String>]
 [-FullName <String>] [-IsGuarded <Boolean>] [-CodeIntegrityPolicy <CodeIntegrityPolicy>]
 [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>] [-TimeZone <Int32>]
 [-Baseline <Baseline[]>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### CreateNewFileServerProfile
```
New-SCPhysicalComputerProfile [-Name] <String> -VirtualHardDisk <VirtualHardDisk> -Domain <String>
 -DomainJoinRunAsAccount <RunAsAccount> -LocalAdministratorCredential <VMMCredential> [-UseAsFileServer]
 -PhysicalComputerNetworkAdapterProfile <PhysicalComputerNetworkAdapterProfile[]>
 [-ComputerAccessRunAsAccount <RunAsAccount>] [-DiskConfiguration <String>]
 [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>] [-VMPaths <String>]
 [-FullName <String>] [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>]
 [-TimeZone <Int32>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### CloneProfile
```
New-SCPhysicalComputerProfile [-Name] <String> -PhysicalComputerProfile <PhysicalComputerProfile>
 [-Description <String>] [-Owner <String>] [-AnswerFile <Script>] [-BypassVHDConversion <Boolean>]
 [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-SCPhysicalComputerProfile** cmdlet creates a profile that is used to deploy an operating system to a computer.

## EXAMPLES

### Example 1: Create a physical computer profile
```
PS C:\>$Account = Get-SCRunaAsAccount -Name "CloudAdmin" 
PS C:\>$Credential = Get-Credential "Contoso\ServiceAdmin" 
PS C:\>$AdapterProfile = Get-SCPhysicalComputerNetworkAdapterProfile -ID "eede207d-d263-4212-ad32-fd29b5a1a6ce" 
PS C:\>$Vhd = Get-SCVirtualHardDisk -Name "Win2012stdGen1template_disk_1.vhdx" 
PS C:\>New-SCPhysicalComputerProfile -Name "ContosoHostProfile" -Domain "contoso.com" -DomainJoinRunAsAccount $Account -LocalAdministratorCredential $Credential -PhysicalComputerNetworkAdapterProfile $AdapterProfile -UseAsVMHost -VirtualHardDisk $Vhd
```

The first command gets the Run As account object and stores it in a variable named $Account.

The second command creates a Windows PowerShell credentials object for the account Contoso\ServiceAdmin and stores it in the $Credential variable.
You must supply the password for the ServiceAdmin account to the Get-Credential cmdlet.

The third command creates an object reference to the physical computer network adapter profile that has the specified ID and stores it in the $AdapterProfile variable.

The fourth command creates an object reference by using the Get-SCVirtualHardDisk cmdlet.
This object references is associated with the virtual hard disk Win2012stdGen1template_disk_1.vhdx.

The final command creates a physical computer profile named ContosoHostProfile based on the values from previous commands.

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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerAccessRunAsAccount
Specifies the computer access Run As account to use to deploy the computer.
This Run As account is added to the machine as a local administrator and used to manage the machine.

```yaml
Type: RunAsAccount
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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

Example format: `-DiskConfiguration "MBR=1:PRIMARY:QUICK:4:FALSE:OS::0:BOOTPARTITION;"`

You must be sure to specify the correct cluster size.
In the example above, the cluster size is 0.
If you do not specify a cluster size, VMM uses the default of 512 bytes, which may be unsuitable to configure advanced format disks.

```yaml
Type: String
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewFileServerProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainJoinRunAsAccount
Specifies a Run As account that has permission to join the specified domain.

```yaml
Type: RunAsAccount
Parameter Sets: CreateNewHostProfileData, CreateNewFileServerProfile
Aliases: 

Required: True
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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

### -JoinWorkgroup
Indicates that this operation joins a workgroup.

```yaml
Type: SwitchParameter
Parameter Sets: CreateNewWorkgroupHostProfileData
Aliases: 

Required: True
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
Aliases: 

Required: True
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

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationName
Specifies the name of the organization for the person in whose name a virtual machine is registered.

```yaml
Type: String
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PhysicalComputerProfile
Specifies a profile that is used to deploy an operating system to a computer.

```yaml
Type: PhysicalComputerProfile
Parameter Sets: CloneProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAsFileServer
Marks the profile as a file server profile.

```yaml
Type: SwitchParameter
Parameter Sets: CreateNewFileServerProfile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseAsVMHost
Marks the profile as a virtual machine host profile.

```yaml
Type: SwitchParameter
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData
Aliases: 

Required: True
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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
Parameter Sets: CreateNewHostProfileData, CreateNewWorkgroupHostProfileData, CreateNewFileServerProfile
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

### PhysicalComputerProfile
This cmdlet returns a **PhysicalComputerProfile** object.

## NOTES

## RELATED LINKS

[Get-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Get-SCPhysicalComputerProfile.md)

[Get-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[Remove-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Remove-SCPhysicalComputerProfile.md)

[Set-SCPhysicalComputerProfile](xref:VirtualMachineManager/v1/Set-SCPhysicalComputerProfile.md)

