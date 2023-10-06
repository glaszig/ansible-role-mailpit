# Test your role with vagrant

Test your role with vagrant

## Prerequisites

  * Virtualbox is installed
  * Vagrant is installed

## Test process

```
cd vagrant
vagrant up
```

The vagrant role will be applied automatically during the vagrant up process.

### Test with molecule from inside vagrant

```
vagrant ssh
cd /etc/ansible/roles/ansible-role-mailpit
molecule test --all
```

### Test the frontend

```
vagrant@mailpit:~$ telnet localhost 1025
Trying 127.0.0.1...
Connected to localhost.
Escape character is '^]'.
220 mailpit Mailpit ESMTP Service ready
mail from: <abc@example.com>
250 2.1.0 Ok
rcpt to: <mail@example.net>
250 2.1.5 Ok
rcpt to: <irgendwer@example.org>
250 2.1.5 Ok
data
354 Start mail input; end with <CR><LF>.<CR><LF>
From: Test <abc@example.com>
To: xyz <xyz@example.com>
Subject: Test

test
.
250 2.0.0 Ok: queued
quit
221 2.0.0 mailpit Mailpit ESMTP Service closing transmission channel
Connection closed by foreign host.
```
