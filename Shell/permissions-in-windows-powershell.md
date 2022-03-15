## Windows Permissions
- Read - lets you see that a file exists, and allows you to read its contents
- Read and execute - lets you read and run files
- List folder contents - alias for read & execute for a directory
- Write - lets you make changes to a file
- Modify - umbrella for read, execute, and write
- Full control - all permissions of modify and adds ability to take ownership of file


### Check permissions of folder

``` Powershell
PS C:\Users\Mika> icacls C:\Users\tanmi\Dev

# output: sees user accounts that have access to path
C:\Users\tanmi\Dev 
NT AUTHORITY\SYSTEM:(I)(OI)(CI)(F)
BUILTIN\Administrators:(I)(OI)(CI)(F)
MIKS-PC\tanmi:(I)(OI)(CI)(F)

```

Get help on icacls command
``` Powershell
PS C:\Users\Mika> icacls /?

# shows descriptions of commands and legend
```

### Modifying permissions

Give access to a user
``` Powershell
PS C:\Users\Mika> icacls 'C:\Vacation Pictures\' /grant 'Everyone: (OI)(CI)(R)' 


```

Remove permissions
``` Powershell
PS C:\Users\Mika> icacls 'C:\Vacation Pictures\' /remove Everyone


```

### Special permissions
- simple permissions - sets of special or specific permissions
- special permissions - refer to specific actions that users can perform 
![[Pasted image 20220311174427.png]]

View special permissions
``` Powershell
PS C:\Users\Mika> icacls 'C:\Windows\Temp' 

# allows user to store temporary files
# must not allow user to delete other users' files

```

Source: Notes from [Google Operating Systems and You (Coursera)]([Operating Systems and You: Becoming a Power User | Coursera](https://www.coursera.org/learn/os-power-user))
