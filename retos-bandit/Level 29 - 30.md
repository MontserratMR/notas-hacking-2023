## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Datos Acceso
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

## Solución
```
bandit29@bandit:~$ cd /tmp
bandit29@bandit:/tmp$ mkdir montsemar
bandit29@bandit:/tmp$ cd montsemar
bandit29@bandit:/tmp/montsemar$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/montsemar$ ls
repo
bandit29@bandit:/tmp/montsemar$ cd repo
bandit29@bandit:/tmp/montsemar/repo$ ls
README.md
bandit29@bandit:/tmp/montsemar/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/montsemar/repo$ git log
commit 0afe3501277395fbfa017480925edee3df6e8bb5 (HEAD -> master, origin/master, origin/HEAD)
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    fix username

commit c2606dfc0aef7179bf1ccd6cffa9ed19151facb4
Author: Ben Dover <noone@overthewire.org>
Date:   Tue Feb 21 22:03:11 2023 +0000

    initial commit of README.md
bandit29@bandit:/tmp/montsemar/repo$ git checkout c2606dfc0aef7179bf1ccd6cffa9ed19151facb4
Note: switching to 'c2606dfc0aef7179bf1ccd6cffa9ed19151facb4'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at c2606df initial commit of README.md
bandit29@bandit:/tmp/montsemar/repo$ ls
README.md
bandit29@bandit:/tmp/montsemar/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit29
- password: <no passwords in production!>

bandit29@bandit:/tmp/montsemar/repo$ git branch -a
* (HEAD detached at c2606df)
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/montsemar/repo$ git checkout dev
Previous HEAD position was c2606df initial commit of README.md
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/montsemar/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```

## Notas Adicionales
Como puede estar en otro branch, lo checamos con el comando git branch.

## Referencias
