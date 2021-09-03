## Two vulnerabilities found in Mikrotik RouterOS
```
 Affected Versions: before 6.47 (stable release tree)
 Affected Services: 1. nova/ftpd
                    2. nova/smb
```
1. FTP vulnerability: it is a memory exhausted vulnerability. The ftpd process doesn't check the request length, By sending a very long payload in the first ftp request,  it can cause the reboot of the system.The payload content doesn't need to be a valid ftp request, anything is possible, and it doesn't require the authentication.

2. SMB vulnerability: it is a memory exhausted vulnerability. The smb process doesn't free a malloc memory, by sending the Session Setup Requset packet repeatedly, it can cause the reboot of the system. The Session Setup Requset needs to be updated the message id field when sending the request repeatedly. It doesn't require the authen


### Disclosure timeline
```
2020/07/02    reported the two issues to the vendor
2020/07/02    vendor requested me to provide PoCs
2020/07/02    provided two PoCs to the vendor
2020/07/03    vendor reproduced the PoC's and said they will fix them as soon as possible.
2020/07/17    vendor has fixed the problem in v6.47.1
```
