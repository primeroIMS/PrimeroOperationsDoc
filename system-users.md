# System users

In order to perform system maintenance, system support staff will need to log on to the Linux server.

The system allows remote logon via SSH for the user **ubuntu**. This user has passwordless sudo \(superuser\) privileges and can be used to run system security upgrades and administer services. Designated support staff will be granted access to this user via public SSH keys.

In order to grant access to the **ubuntu** user, append the designated support person’s key to the file /home/ubuntu/.ssh/authorized\_keys. For more on SSH key access to linux refer to the following guide: [https://www.linode.com/docs/security/use-public-key-authentication-with-ssh](https://www.linode.com/docs/security/use-public-key-authentication-with-ssh).

Some administrative tasks such as data cleanup tasks must be done with the **primero** system user. This user is distinct from the application primero user. To switch from the **ubuntu** user to the **primero** user:

`$ sudo -Hu primero bash`

`$ source ~/.rvm/scripts/rvm`





