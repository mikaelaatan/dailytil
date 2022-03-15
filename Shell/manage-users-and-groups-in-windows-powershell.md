### Viewing Users and Groups

See list of users in the computer
```Powershell
PS C:\Users\Mika> Get-LocalUser

Name               Enabled Description
----               ------- -----------
Administrator      False   Built-in account for administering the computer/domain
DefaultAccount     False   A user account managed by the system.
Guest              False   Built-in account for guest access to the computer/domain
tanmi              True
WDAGUtilityAccount False   A user account managed and used by the system for Windows Defender Application Guard scen...

```

See list of groups
```Powershell
PS C:\Users\Mika> Get-LocalGroup

Name                                Description
----                                -----------
Access Control Assistance Operators Members of this group can remotely query authorization attributes and permission...
Administrators                      Administrators have complete and unrestricted access to the computer/domain
Backup Operators                    Backup Operators can override security restrictions for the sole purpose of back...

```

See who are members of certain group (administrator)
``` Powershell
PS C:\Users\Mika> Get-LocalGroupMember Administrators

ObjectClass Name                  PrincipalSource
----------- ----                  ---------------
User        MIKS-PC\Administrator Local
User        MIKS-PC\tanmi         MicrosoftAccount
```

### Adding and removing users - Windows

Adding a user and force user to change password on next logon
```Powershell
PS C:\Users\Mika> net user username * /add /logonpasswordchg:yes
Type a password for the user:
Retype the password to confirm:
The command completed successfully.

# confirm if added by using Get-LocalUser

```

Remove accounts
```Powershell
PS C:\Users\Mika> net user username /del 

# or

PS C:\Users\Mika> Remove-LocalUser username

```

### Managing Passwords - Windows CLI
* Resetting password will cause loss of information
![[Pasted image 20220311140004.png]]

Change password of a user
```Powershell
PS C:\Users\Mika> net user username *
Type a password for the user:

# prompts the user to type the password

```

Prompt user to change password at login
```Powershell
PS C:\Users\Mika> net user username /logonpasswordchg:yes
The command completed successfully

```

Source: Own notes from [Google Operating Systems and You (Coursera)]([Operating Systems and You: Becoming a Power User | Coursera](https://www.coursera.org/learn/os-power-user))
*Additional Reading:* [Selecting Secure Passwords | Microsoft Docs](https://docs.microsoft.com/en-us/previous-versions/tn-archive/cc875839(v=technet.10)?redirectedfrom=MSDN)
