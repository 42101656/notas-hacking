# Level 13

## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de acceso al nivel
User: bandit12
Password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
Host: bandit.labs.overthewire.org  
Port: 2220

## Solución
```
lsbandit12@bandit:~$ ls -lah
total 24K
drwxr-xr-x  2 root     root     4.0K Oct  5 06:19 .
drwxr-xr-x 70 root     root     4.0K Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3.7K Jan  6  2022 .bashrc
-rw-r-----  1 bandit13 bandit12 2.6K Oct  5 06:19 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit12@bandit:~$ mkdir /tmp/42101656
bandit12@bandit:~$ cp ./datat.txt /tmp/42101656
cp: cannot stat './datat.txt': No such file or directory
bandit12@bandit:~$ cp ./data.txt /tmp/42101656
bandit12@bandit:~$ cd /tmp/42101656
bandit12@bandit:/tmp/42101656$ ls -lah
total 408K
drwxrwxr-x   2 bandit12 bandit12 4.0K Feb 20 18:45 .
drwxrwx-wt 110 root     root     396K Feb 20 18:45 ..
-rw-r-----   1 bandit12 bandit12 2.6K Feb 20 18:45 data.txt
bandit12@bandit:/tmp/42101656$ mv data.txt data2.txt
bandit12@bandit:/tmp/42101656$ xxd -r data2.txt > data
bandit12@bandit:/tmp/42101656$ file datat
datat: cannot open `datat' (No such file or directory)
bandit12@bandit:/tmp/42101656$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/42101656$ mv data data.gz
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data.gz
bandit12@bandit:/tmp/42101656$ gzip -d data.gz
bandit12@bandit:/tmp/42101656$ ls
data  data2.txt
bandit12@bandit:/tmp/42101656$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/42101656$ mv data data.bz2
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data.bz2
bandit12@bandit:/tmp/42101656$ bzip2 -d data.bz2
bandit12@bandit:/tmp/42101656$ ls
data  data2.txt
bandit12@bandit:/tmp/42101656$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/42101656$ mv data data.gz
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data.gz
bandit12@bandit:/tmp/42101656$ gzip -d data.gz
bandit12@bandit:/tmp/42101656$ ls
data  data2.txt
bandit12@bandit:/tmp/42101656$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/42101656$ mv data data.tar
bandit12@bandit:/tmp/42101656$ tar xf data.tar
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data5.bin  data.tar
bandit12@bandit:/tmp/42101656$ rm data.tar
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data5.bin
bandit12@bandit:/tmp/42101656$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/42101656$ mv data5.bin data5.tar
bandit12@bandit:/tmp/42101656$ tar xf data5.tar
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data5.tar  data6.bin
bandit12@bandit:/tmp/42101656$ rm data5.tar
bandit12@bandit:/tmp/42101656$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/42101656$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/42101656$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data6
bandit12@bandit:/tmp/42101656$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/42101656$ mv data6 data6.tar
bandit12@bandit:/tmp/42101656$ tar xf data6.tar
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data6.tar  data8.bin
bandit12@bandit:/tmp/42101656$ rm data6.tar
bandit12@bandit:/tmp/42101656$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/42101656$ mv data8.bin data9.gz
bandit12@bandit:/tmp/42101656$ gzip -d data9.gz
bandit12@bandit:/tmp/42101656$ ls
data2.txt  data9
bandit12@bandit:/tmp/42101656$ file data9
data9: ASCII text
bandit12@bandit:/tmp/42101656$ cat data9
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/42101656$
```
## Notas adicionales
* xxd es un comando que se utiliza principalmente para crear y analizar volcados hexadecimales de archivos. 
* La opcion -r del comando xxd se puede utilizar para revertir el proceso y convertir un volcado hexadecimal nuevamente a formato binario.
## Referencias
https://www.geeksforgeeks.org/xxd-command-in-linux/
