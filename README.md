# ssh_lockout_check
Tool for checking how many failed authentication attempts will cause an account to become locked

```
$ ./ssh_lockout_check.py example.com username superstrongpassword 100
Trying 0 bad passwords followed by a good one
Authentication successful after 0 bad passwords

Trying 1 bad passwords followed by a good one.
Authentication successful after 1 bad passwords

Trying 2 bad passwords followed by a good one..
Authentication successful after 2 bad passwords

Trying 3 bad passwords followed by a good one...
Authentication successful after 3 bad passwords

Trying 4 bad passwords followed by a good one....
Authentication successful after 4 bad passwords

Trying 5 bad passwords followed by a good one.....
Authentication failed after 5 bad passwords. Account may be locked
```
