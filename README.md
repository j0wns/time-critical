# time-critical
Command line utilities for converting and reading time formats.
Sometimes you just need to know what time it was.

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

