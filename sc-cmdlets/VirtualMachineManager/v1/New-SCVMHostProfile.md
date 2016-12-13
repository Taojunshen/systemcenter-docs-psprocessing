---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: ./Get-SCRunAsAccount.md
schema: 2.0.0
ms.assetid: 1697F623-0F19-4314-9F04-5897C046E4D1
updated_at: 12/13/2016 10:42 PM
ms.date: 12/13/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMHostProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/master/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMHostProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/ea9507ac2178040476af5407227db8cb97701ea9/systemcenter-cmdlets/VirtualMachineManager/v1/New-SCVMHostProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCVMHostProfile

## SYNOPSIS
Creates a host profile.

## SYNTAX

### CreateNewHostProfileData (Default)
```
New-SCVMHostProfile [-VMHostNetworkAdapterProfile <PhysicalComputerNetworkAdapterProfile[]>] [-Name] <String>
 -VirtualHardDisk <VirtualHardDisk> -Domain <String> -DomainJoinRunAsAccount <RunAsAccount>
 -LocalAdministratorCredential <VMMCredential> [-ComputerAccessRunAsAccount <RunAsAccount>]
 [-DiskConfiguration <String>] [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>]
 [-VMPaths <String>] [-FullName <String>] [-IsGuarded <Boolean>] [-CodeIntegrityPolicy <CodeIntegrityPolicy>]
 [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>] [-TimeZone <Int32>]
 [-Baseline <Baseline[]>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### CloneProfile
```
New-SCVMHostProfile -VMHostProfile <PhysicalComputerProfile> [-Name] <String> [-Description <String>]
 [-Owner <String>] [-AnswerFile <Script>] [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### CreateNewWorkgroupHostProfileData
```
New-SCVMHostProfile [-Name] <String> -VirtualHardDisk <VirtualHardDisk> [-JoinWorkgroup]
 -LocalAdministratorCredential <VMMCredential> [-ComputerAccessRunAsAccount <RunAsAccount>]
 [-DiskConfiguration <String>] [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>]
 [-VMPaths <String>] [-FullName <String>] [-IsGuarded <Boolean>] [-CodeIntegrityPolicy <CodeIntegrityPolicy>]
 [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>] [-TimeZone <Int32>]
 [-Baseline <Baseline[]>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

### CreateNewFileServerProfile
```
New-SCVMHostProfile [-Name] <String> -VirtualHardDisk <VirtualHardDisk> -Domain <String>
 -DomainJoinRunAsAccount <RunAsAccount> -LocalAdministratorCredential <VMMCredential>
 [-ComputerAccessRunAsAccount <RunAsAccount>] [-DiskConfiguration <String>]
 [-DriverMatchingTag <System.Collections.Generic.List`1[System.String]>] [-VMPaths <String>]
 [-FullName <String>] [-GuiRunOnceCommands <String[]>] [-OrganizationName <String>] [-ProductKey <String>]
 [-TimeZone <Int32>] [-JobGroup <Guid>] [-Description <String>] [-Owner <String>] [-AnswerFile <Script>]
 [-BypassVHDConversion <Boolean>] [-VMMServer <ServerConnection>] [-RunAsynchronously] [-PROTipID <Guid>]
 [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCVMHostProfile** cmdlet creates a host profile.
Host profiles contain the hardware and operating system configuration settings used to deploy a physical computer as a Hyper-V host.

Before you create a host profile, ensure that the virtual hard disk drive (.vhd) file that you specify exists in a library share.

## EXAMPLES

### Example 1: Create a host profile
```
PS C:\>$VHD = Get-SCVirtualHardDisk -Name "VHD01.vhd"
PS C:\> $RunAsAcct = Get-SCRunAsAccount -Name "RunAsAcct01"
PS C:\> $Credential = Get-Credential
PS C:\> $HostProfile = New-SCVMHostProfile -Name "HostProfile01" -Owner "Contoso\Katarina" -Description "Host Profile 01" -Domain "Contoso.com" -DomainJoinRunAsAccount $RunAsAcct -VirtualHardDisk $VHD -LocalAdministratorCredential $Credential
PS C:\> $HostProfile
```

The first command gets the virtual hard disk object named VHD01.vhd and stores the object in the $VHD variable.

The second command prompts you for credentials.
At the prompt, enter the credentials of an Administrator account.
The command stores the credentials in the $Credential variable.

The third command creates a host profile named HostProfile01 using the virtual hard disk stored in $VHD, and the credentials stored in $Credential.

The last command displays information about the newly created host profile to the user.

### Example 2: Clone an existing host profile
```
PS C:\>$OrigHostProfile = Get-SCVMHostProfile -Name "HostProfile01"
PS C:\> $NewHostProfile = New-SCVMHostProfile -Name "HostProfile02" -VMHostProfile $OrigHostProfile
```

The first command gets the host profile object named HostProfile01 and stores the object in the $OrigHostProfile variable.

The second command copies the host profile stored in $OrigHostProfile, gives it the specified name, and stores the new profile object in the $NewHostProfile variable.

### Example 3: Create a host profile that includes a host network adapter profile
```
PS C:\> $VHDX = Get-SCVirtualHardDisk -Name "VHDX01.vhdx"
PS C:\> $DomainJoinCreds = Get-SCRunAsAccount -Name "DomainJoinRAA"
PS C:\> $LocalAdminCreds = Get-Credential
PS C:\> $HostNetAdapterProf = Get-SCVMHostNetworkAdapterProfile -ID "259f47c7-c5a9-429d-a421-d232f9b34991"
PS C:\> New-SCVMHostProfile -Name "HostProfile03" -Owner "Contoso\Katarina" -Description "Host Profile 03" -Domain "Contoso.com" -DomainJoinRunAsAccount $DomainJoinCreds -VirtualHardDisk $VHDX -LocalAdministratorCredential $LocalAdminCreds -VMHostNetworkAdapterProfile $HostNetAdapterProf
```

The first command gets the virtual hard disk object named VHDX01.vhdx and stores the object in the $VHDX variable.

The second command gets the Run As account object named DomainJoinRAA and stores the object in the $DomainJoinCreds variable.

The third command prompts the user for local administrator credentials and stores the provided credentials in the $LocalAdminCreds variable.

The fourth command gets the host network adapter profile object with the ID of 259f47c7-c5a9-429d-a421-d232f9b34991 and stores the object in the $HostNetAdapterProf variable.

The last command creates a host profile named Host Profile 03 using VHDX01 and the host network adapter profile stored in $HostNetAdapterProf.

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
Specifies an array of **Baseline** objects.

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
Indicates whether a dynamic VHD attached to a host profile is not converted to a fixed type during deployment.

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
Specifies a description for the host profile.

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
Specifies the user name and password for the Local Administrator account (or Linux root account in the case of a Linux-compatible Guest Operating System profile).

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

### -VMHostNetworkAdapterProfile
Specifies a host network adapter profile object.

```yaml
Type: PhysicalComputerNetworkAdapterProfile[]
Parameter Sets: CreateNewHostProfileData
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMHostProfile
Specifies a virtual machine host profile object.

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

### HostProfile
This cmdlet returns a **HostProfile** object.

## NOTES

## RELATED LINKS

[Get-SCRunAsAccount](xref:VirtualMachineManager/v1/Get-SCRunAsAccount.md)

[Get-SCVirtualHardDisk](xref:VirtualMachineManager/v1/Get-SCVirtualHardDisk.md)

[Get-SCVMHostNetworkAdapterProfile](xref:VirtualMachineManager/v1/Get-SCVMHostNetworkAdapterProfile.md)

[Get-SCVMHostProfile](xref:VirtualMachineManager/v1/Get-SCVMHostProfile.md)

[Remove-SCVMHostProfile](xref:VirtualMachineManager/v1/Remove-SCVMHostProfile.md)

[Set-SCVMHostProfile](xref:VirtualMachineManager/v1/Set-SCVMHostProfile.md)

