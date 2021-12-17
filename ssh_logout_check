#!/usr/bin/env python3

import sys

from paramiko import SSHClient, ssh_exception


def attempt_authentication(client, hostname, username, password):
    try:
        client.connect(
                hostname=hostname,
                username=username,
                password=password)
    except ssh_exception.AuthenticationException:
        return False
    else:
        return True


def main():
    if len(sys.argv) != 5:
        sys.exit(
                f'Usage {sys.argv[0]} hostname, username, '
                'password, max_wrong_password')
    hostname = sys.argv[1]
    username = sys.argv[2]
    password = sys.argv[3]
    max_wrong_passwd = int(sys.argv[4])

    client = SSHClient()
    client.load_system_host_keys()

    for i in range(max_wrong_passwd):

        sys.stdout.write(f'Trying {i} bad passwords followed by a good one')
        for i in range(i):
            sys.stdout.write('.')
            attempt_authentication(client, hostname, username, 'wrongpassword')
        print()

        if attempt_authentication(client, hostname, username, password):
            print(f'Authentication successful after {i} bad passwords\n')
        else:
            print(
                    f'Authentication failed after {i} bad '
                    'passwords. Account may be locked')
            break


if __name__ == '__main__':
    main()
