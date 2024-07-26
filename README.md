# time-critical
Command line utilities for converting and reading time formats.
Sometimes you just need to know what time it was.

## Usage

Get current time in a particular format and pipe it to the 'four character' converters.
- Linux Timestamp
  - ltod
  - ltow
- W32/LDAP Timestamp
  - wtod
  - wtol
- DateTime
  - dtol
  - dtow

Getting current time

```
┌──(user@host)-[2024-07-26 16:44:45]-[~]
└─$ get-date                                                                  
Fri 26 Jul 2024 05:19:30 PM UTC
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:19:30]-[~]
└─$ get-date | dtol
1722014379.0000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:19:39]-[~]
└─$ get-date | dtow
133664879810000000
```

Getting Specific Time

```                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:19:42]-[~]
└─$ echo "Thu 1 Jan 1970 12:00:00 AM UTC" | dtol 
0.0000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:20:43]-[~]
└─$ echo "Thu 1 Jan 1970 12:00:00 AM UTC" | dtow
116444736000000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:20:47]-[~]
└─$ echo "Tue 19 Jan 2038 03:14:07 AM UTC"   
Tue 19 Jan 2038 03:14:07 AM UTC
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:21:57]-[~]
└─$ echo "Tue 19 Jan 2038 03:14:07 AM UTC" | dtol
2147483647.0000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:22:01]-[~]
└─$ echo "Tue 19 Jan 2038 03:14:07 AM UTC" | dtow
137919572470000000
```

Sanity checking Epoch

```                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:22:03]-[~]
└─$ echo "Tue 19 Jan 2038 03:14:08 AM UTC" | dtol
2147483648.0000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:22:16]-[~]
└─$ echo "Tue 19 Jan 2038 03:14:08 AM UTC" | dtow
137919572480000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:22:21]-[~]
└─$ echo "Wed 31 Dec 1969 11:59:59 PM UTC" | dtol  
-1.0000000
                                                                                                                                                                                          
┌──(user@host)-[2024-07-26 17:22:53]-[~]
└─$ echo "Wed 31 Dec 1969 11:59:59 PM UTC" | dtow
116444735990000000
                                               
```

## Supported Formats
1. datetime
2. *nux epoch
3. LDAP W32 Filetime

## Getters
Print the current time in a specified format
* get-date
* get-linuxepoch
* get-w43ldapfiletime

## Converters
* dtol - date to linux epoch
* ltow - linux epoch to w32 ldap filetime
* wtol - w32 ldap file to linux epoch
* ltod - linux epoch to date
* dtow - date to w32 ldap filetime
* wtod - w32 ldap filetime to date

### Conversion Primitives
* date
* expr
* cut
* rev
* echo

