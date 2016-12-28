---
external help file: Microsoft.SystemCenter.VirtualMachineManager.dll-Help.xml
online version: 
schema: 2.0.0
ms.assetid: 24489E02-AC3A-478D-8F37-535AC60DD14F
updated_at: 12/22/2016 3:56 PM
ms.date: 12/22/2016
content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGuestOSProfile.md
original_content_git_url: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/live/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGuestOSProfile.md
gitcommit: https://github.com/MicrosoftDocs/systemcenter-docs-powershell/blob/96e5647587661652225fbdd2c797cd4d59d542bc/systemcenter-cmdlets/SystemCenter2016/VirtualMachineManager/vlatest/New-SCGuestOSProfile.md
ms.topic: reference
author: tarameyer
ms.author: cfreeman
keywords: powershell, cmdlet
manager: carmonm
open_to_public_contributors: true
ms.service: system-center
---

# New-SCGuestOSProfile

## SYNOPSIS
Creates a guest operating system profile for use in VMM.

## SYNTAX

### Default (Default)
```
New-SCGuestOSProfile [-Shielded <Boolean>] [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>]
 [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>]
 [-ProductKey <String>] [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>]
 [-RemoveServerFeatures] [-GuestOSProfile <GuestOSProfile>] [-Owner <String>] [-UserRole <UserRole>]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-LinuxDomainName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SSHKeyFile
```
New-SCGuestOSProfile [-Shielded <Boolean>] [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>]
 [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKey <SSHKey>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures]
 [-GuestOSProfile <GuestOSProfile>] [-Owner <String>] [-UserRole <UserRole>]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-LinuxDomainName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### SSHKeyString
```
New-SCGuestOSProfile [-Shielded <Boolean>] [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>]
 [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>] [-LinuxAdministratorSSHKeyString <String>]
 [-VMMServer <ServerConnection>] [-Name] <String> [-Description <String>] [-FullName <String>]
 [-OrganizationName <String>] [-ComputerName <String>] [-ProductKey <String>]
 [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>] [-RemoveServerFeatures]
 [-GuestOSProfile <GuestOSProfile>] [-Owner <String>] [-UserRole <UserRole>]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-LinuxDomainName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Domain
```
New-SCGuestOSProfile [-Shielded <Boolean>] [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>]
 [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>]
 [-ProductKey <String>] [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>]
 [-RemoveServerFeatures] -Domain <String> [-DomainJoinCredential <VMMCredential>]
 [-GuestOSProfile <GuestOSProfile>] [-Owner <String>] [-UserRole <UserRole>]
 [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-LinuxDomainName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

### Workgroup
```
New-SCGuestOSProfile [-Shielded <Boolean>] [-GuiRunOnceCommands <String[]>] [-MergeAnswerFile <Boolean>]
 [-AnswerFile <Script>] [-OperatingSystem <OperatingSystem>] [-VMMServer <ServerConnection>] [-Name] <String>
 [-Description <String>] [-FullName <String>] [-OrganizationName <String>] [-ComputerName <String>]
 [-ProductKey <String>] [-LocalAdministratorCredential <VMMCredential>] [-TimeZone <Int32>]
 [-RemoveServerFeatures] [-Workgroup <String>] [-GuestOSProfile <GuestOSProfile>] [-Owner <String>]
 [-UserRole <UserRole>] [-AutoLogonCredential <RunAsAccount>] [-AutoLogonCount <UInt32>] [-DisableAutoLogon]
 [-UnattendSettings <System.Collections.Generic.Dictionary`2[System.String,System.String]>]
 [-DomainJoinOrganizationalUnit <String>] [-RemoveDomainJoinOrganizationalUnit] [-LinuxDomainName <String>]
 [-RunAsynchronously] [-PROTipID <Guid>] [-JobVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-SCGuestOSProfile** cmdlet creates a guest operating system profile for use in Virtual Machine Manager (VMM).
A guest operating system is the operating system on a virtual machine, in contrast to a host operating system which is on the physical host computer on which one or more virtual machines are deployed.

A guest operating system profile stores operating system configuration information.
A profile consists of a set of properties containing the most common settings specified in an unattended answer file (such as a Sysprep.inf or an Unattend.xml file).

You can create a standalone guest operating system profile or customize a template or virtual machine to include guest operating system profile settings.
The **New-SCGuestOSProfile** cmdlet stores the new guest operating system profile object in the VMM library.

You can create a guest operating system profile based on default settings, based on an existing guest operating system profile, or you can customize settings as you create the profile.
If you specify no parameters except the Name parameter, the **New-SCGuestOSProfile** cmdlet creates a default guest operating system profile object.

## EXAMPLES

### Example 1: Create a default guest operating system profile
```
PS C:\> $OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Enterprise"}
PS C:\> New-SCGuestOSProfile -Name "NewOSProfile01" -OperatingSystem $OS
```

The first command gets the operating system object named "64-bit edition of Windows Server 2008 R2 Enterprise" from VMMServer01 and stores the object in the $OS variable.

The second command creates a default guest operating system profile named NewProfile01 and specifies the name of the operating system.

### Example 2: Create a guest operating system profile to use to join a virtual machine to a domain
```
PS C:\> $DomainCredential = Get-SCRunAsAccount -Name "RunAsAccount01"
PS C:\> $OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Enterprise"} 
PS C:\> New-SCGuestOSProfile -Name "NewOSProfile02" -JoinDomain "Contoso.com" -DomainJoinCredential $DomainCredential -OperatingSystem $OS
```

The first command gets the Run As account object named RunAsAccount01 and stores the object in the $DomainCredential variable.

The second command gets the operating system object named 64-bit edition of Windows Server 2008 R2 Enterprise from VMMServer01 and stores the object in the $OS variable.

The last command creates a guest operating system profile called NewOSProfile02 and specifies the name of the operating system.
When you use NewOSProfile02 to create a virtual machine, the profile uses the specified Run As account to join the virtual machine to the Contoso.com domain.

Note: If you provide a **PSCredential** object instead of a RunAs account for the *DomainJoinCredential* parameter, it is recommended practice to use only an account with limited rights for automatically joining a virtual machine to a domain because the domain account name and password appear briefly in plain text on the host server.

### Example 3: Clone an existing guest operating system profile
```
PS C:\> $OSProfile = Get-SCGuestOSProfile -Name "NewOSProfile02"
PS C:\> $OS = Get-SCOperatingSystem -VMMServer "VMMServer01.contoso.com" | where {$_.Name -eq "64-bit edition of Windows Server 2008 R2 Datacenter"} 
PS C:\> New-SCGuestOSProfile -Name "NewOSProfile03" -GuestOSProfile $OSProfile -ComputerName "Contoso03" -OperatingSystem $OS
```

The first command gets the guest OS profile object named NewOSProfile02 and stores the object in the $OSProfile variable.

The second command gets the operating system object named 64-bit edition of Windows Server 2008 R2 Datacenter and stores the object in the $OS variable.

The last command creates guest operating system profile named NewOSProfile03, which is based on NewOSProfile02, but modifies the computer name and specifies a different name for the operating system.
All other settings in NewOSProfile03 are identical to those in NewOSProfile02.

### Example 4: Create a Linux guest operating system profile and set the Linux DNS domain name
```
PS C:\> $OS = Get-SCOperatingSystem -VMMServer "VMMServer01.Contoso.com" | where {$_.Name -eq "CentOS Linux 6 (64 bit)"} 
PS C:\> New-SCGuestOSProfile -Name "My CentOS Profile" -LinuxDomainName "contoso.com" -OperatingSystem $os
```

The first command gets the operating system object named CentOS Linux 6 (64 bit) from VMMServer01 and stores the object in the $OS variable.

The second command creates a guest operating system profile named My CentOS Profile and specifies the name of the operating system and the Linux DNS domain name.
When you use the My CentOS Profile to create a virtual machine, the profile  uses the specified Linux DNS domain name.

## PARAMETERS

### -AnswerFile
Specifies a script object stored in the VMM library to use as an answer file.
The name of the answer file script depends on the operating system that you want to install on a virtual machine: 

- Sysprep.inf.
Windows XP, Windows Server 2000, or Windows Server 2003
- Unattend.xml.
Windows Vista, Windows 7, or Windows Server 2008

```yaml
Type: Script
Parameter Sets: (All)
Aliases: SysPrepFile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -AutoLogonCount
Specifies the number of times that Windows should automatically log the administrator specified in the answer file on to the console session.

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

### -AutoLogonCredential
Specifies the Run As account contained in the answer file that Windows uses to log on to the console session when automatic administrator logon is enabled.

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

### -ComputerName
Specifies the name of a computer that VMM can uniquely identify on your network.
The acceptable values for this parameter are:

- FQDN
- IPv4 or IPv6 address
- NetBIOS name

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

### -Description
Specifies a description for the guest operating system profile.

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

### -DisableAutoLogon
Indicates that this cmdlet disables automatic administrator logon.

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

### -Domain
Specifies a fully qualified domain name (FQDN) for an Active Directory domain. 



Example format: `-Domain "Domain01.Corp.Contoso.com"`

```yaml
Type: String
Parameter Sets: Domain
Aliases: JoinDomain

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainJoinCredential
Specifies the user name and password of an account that has permission to join a computer to the domain.
We recommend that you use a limited rights account joining computers to the domain.
This includes both virtual and physical computers.

You can use the current parameter to specify credentials on a **VMHostProfile** for joining a physical host computer to the domain, or to specify credentials, on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine, for joining a virtual machine to the domain.

```yaml
Type: VMMCredential
Parameter Sets: Domain
Aliases: JoinDomainCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainJoinOrganizationalUnit
Specifies the organizational unit to which the computer is joined during an unattended mini-setup.

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

### -GuestOSProfile
Specifies a guest operating system profile object.

```yaml
Type: GuestOSProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -LinuxAdministratorSSHKey
Specifies the public key file for a Linux SSH Key.

```yaml
Type: SSHKey
Parameter Sets: SSHKeyFile
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxAdministratorSSHKeyString
Specifies a Linux administrator SSH key as a string.

```yaml
Type: String
Parameter Sets: SSHKeyString
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LinuxDomainName
Specifies a fully qualified domain name (FQDN) to use in conjunction with Linux operating system specialization. 



Example format: `-LinuxDomainName "Domain01.Corp.Contoso.com"`

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
Specifies the user name and password for the Local Administrator account (or Linux root account in the case of a Linux-compatible guest operating system profile).

Specifying credentials on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine overrides any existing Administrator password.

```yaml
Type: VMMCredential
Parameter Sets: (All)
Aliases: AdminPasswordCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MergeAnswerFile
Indicates whether this cmdlet merges the answer file together with guest operating system settings.
The default value is $True.
VMM console uses this parameter.
Do not specify this parameter.

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

### -OperatingSystem
Specifies the type of operating system for a virtual machine.
To get the names of all available operating systems in VMM, type `Get-SCOperatingSystem`.

```yaml
Type: OperatingSystem
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrganizationName
Specifies the name of the organization for the person in whose name a virtual machine is registered.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OrgName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Owner
Specifies the owner of a VMM object in the form of a valid domain user account. 

- Example format: `-Owner "Contoso\PattiFuller"`
- Example format: `-Owner "PattiFuller@Contoso"`

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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveDomainJoinOrganizationalUnit
Indicates that this cmdlet removes the organizational unit that the computer joined during setup.

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

### -RemoveServerFeatures
Indicates that this cmdlet removes all server roles and features from a template.

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

### -Shielded
Indicates whether the object is shielded.

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

### -TimeZone
Specifies a number (an index) that identifies a geographical region that shares the same standard time.
For a list of time zone indexes, see [Microsoft Time Zone Index Values](http://go.microsoft.com/fwlink/?LinkId=120935) at `http://go.microsoft.com/fwlink/?LinkId=120935`.
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

### -UnattendSettings
Specifies a key/value pair consisting of **String**, **String**.

```yaml
Type: System.Collections.Generic.Dictionary`2[System.String,System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserRole
Specifies a user role object.

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

### -Workgroup
Specifies on a new or existing template, on a new or existing guest operating system profile, or on a new virtual machine the name of the workgroup to which you want to join a virtual machine.
You can use this parameter to override the existing value on a template or on a guest operating system profile.

```yaml
Type: String
Parameter Sets: Workgroup
Aliases: JoinWorkgroup

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

### GuestOSProfile
This cmdlet returns a **GuestOSProfile** object.

## NOTES

## RELATED LINKS

[Get-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCGuestOSProfile.md)

[Get-SCOperatingSystem](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCOperatingSystem.md)

[Get-SCRunAsAccount](xref:SystemCenter2016/VirtualMachineManager/vlatest/Get-SCRunAsAccount.md)

[Remove-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Remove-SCGuestOSProfile.md)

[Set-SCGuestOSProfile](xref:SystemCenter2016/VirtualMachineManager/vlatest/Set-SCGuestOSProfile.md)

