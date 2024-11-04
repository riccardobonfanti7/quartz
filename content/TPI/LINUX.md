# GUIDA COMANDI 

>La shell più comunemente utilizzata per i [[SO]] Linux è chiamata shell Bash([[CLI]]).

Il ~ simbolo viene utilizzato come abbreviazione per la directory home dell'utente. 

In questa guida potrai trovare i comandi fondamentali di Linux con i relativi esempi e spiegazioni di ciò che avviene.

**comando [opzioni] [argomenti]**

___

  

**pwd** [OPTIONS]

Il comando pwd <u>stampa la directory di lavoro</u>, che è la posizione corrente dell'utente all'interno del filesystem.

```

sysadmin@localhost:~$ pwd

/home/sysadmin

```

___

**cd** [options] [path]

Per navigare nel filesystem, usa **cd** command.

```

sysadmin@localhost:~$ cd Documents

sysadmin@localhost:~/Documents$

```

  

Il carattere ~ è equivalente a /home/sysadmin, che rappresenta la directory home dell'utente.

  

Se utilizzato senza argomenti, il comando cd porterà l'utente alla propria directory home.

```

sysadmin@localhost:~/Documents$ cd

sysadmin@localhost:~$

```

Puoi mettere anche un percorso di tipo assoluto utilizzando il comando cd:

```

sysadmin@localhost:~/Documents$ cd /home/sysadmin/Documents/School/Art

sysadmin@localhost:~/Documents/School/Art$

```

Due caratteri punto **..** rappresentano sempre una directory più in alto rispetto alla directory corrente.

```

sysadmin@localhost:~/Documents/School/Art$ cd ..

sysadmin@localhost:~/Documents/School$

```

___

ls [OPTION]... [FILE]...

Questo comando **ls** viene utilizzato per visualizzare il contenuto di una directory e può fornire informazioni dettagliate sui file.

```

sysadmin@localhost:~$ ls

Desktop Documents Downloads Music Pictures Public

```

Il comando **ls** può essere utilizzato anche <u>per elencare il contenuto di qualsiasi directory nel filesystem</u>. Fornire il percorso della directory come argomento:

```

sysadmin@localhost:~$ ls /var

backups cache lib local lock log mail opt run spool tmp

```

Il comando ls <u>omette i file nascosti</u> per impostazione predefinita. Un file nascosto è qualsiasi file (o directory) che inizia con un punto(.) carattere.

```

sysadmin@localhost:~$ ls -a

. .bashrc .selected_editor Downloads Public

.. .cache Desktop Music Templates

.bash_logout .profile Documents Pictures Videos

```

A ogni file sono associati dettagli chiamati [[metadati]].

Per visualizzare queste informazioni, utilizzare ** l'opzione -l** del comando ls.

```

sysadmin@localhost:~$ ls -l /var/log/

total 900

-rw-r--r-- 1 root root 15322 Dec 10 21:33 alternatives.log

drwxr-xr-x 1 root root 4096 Jul 19 06:52 apt

-rw-r----- 1 syslog adm 371 Dec 15 16:38 auth.log

-rw-r--r-- 1 root root 35330 May 26 2018 bootstrap.log

-rw-rw---- 1 root utmp 0 May 26 2018 btmp

-rw-r----- 1 syslog adm 197 Dec 15 16:38 cron.log

-rw-r--r-- 1 root adm 85083 Dec 10 21:33 dmesg

-rw-r--r-- 1 root root 351960 Jul 19 06:52 dpkg.log

-rw-r--r-- 1 root root 32064 Dec 10 21:33 faillog

drwxr-xr-x 2 root root 4096 Jul 19 06:51 journal

-rw-rw-r-- 1 root utmp 292584 Dec 15 16:38 lastlog

-rw-r----- 1 syslog adm 14185 Dec 15 16:38 syslog

-rw------- 1 root root 64128 Dec 10 21:33 tallylog

-rw-rw-r-- 1 root utmp 384 Dec 15 16:38 wtmp

```

```

sysadmin@localhost:~$ ls -ld

drwxr-xr-x 1 sysadmin sysadmin 224 Nov 7 17:07 .

```

___
Per eseguire un elenco ricorsivo, utilizzare **l'opzione -R** del comando ls:

```

sysadmin@localhost:~$ ls -R /etc/ppp

/etc/ppp:

ip-down.d ip-up.d

  

/etc/ppp/ip-down.d:

bind9

  

/etc/ppp/ip-up.d:

bind9

```

___
Per ordinare i file in base alla dimensione, possiamo utilizzare **l'opzione -S**.

```

sysadmin@localhost:~$ ls -S /etc/ssh

moduli ssh_host_ed25519_key ssh_host_ecdsa_key.pub

sshd_config ssh_host_rsa_key.pub ssh_host_ed25519_key.pub

ssh_host_rsa_key ssh_import_id

ssh_config ssh_host_ecdsa_key

```

Potrebbe anche essere utile utilizzare **l'opzione -h** per visualizzare le dimensioni dei file leggibili dall'uomo.

  

**L'opzione -t** ordina i file in base all'ora in cui sono stati modificati.