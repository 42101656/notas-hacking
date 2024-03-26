## Objetivo
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)

## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir time_machine

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd time_machine/

kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine$ wget https://artifacts.picoctf.net/c_titan/160/challenge.zip
--2024-03-16 18:34:22--  https://artifacts.picoctf.net/c_titan/160/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17740 (17K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip                                              100%[=======================================================================================================================================>]  17.32K  --.-KB/s    in 0s      

2024-03-16 18:34:24 (56.8 MB/s) - ‘challenge.zip’ saved [17740/17740]


kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt     
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469  
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2  
   creating: drop-in/.git/objects/89/
 extracting: drop-in/.git/objects/89/d296ef533525a1378529be66b22d6a2c01e530  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  

kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine$ cd drop-in/

kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine/drop-in$ ls -la
total 16
drwxr-xr-x 3 kali kali 4096 Mar 11 20:07 .
drwxr-xr-x 3 kali kali 4096 Mar 16 18:34 ..
drwxr-xr-x 8 kali kali 4096 Mar 11 20:07 .git
-rw-r--r-- 1 kali kali   87 Mar 11 20:07 message.txt

kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine/drop-in$ cat message.txt 
This is what I was working on, but I'd need to look at my commit history to know why...
kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine/drop-in$ git log
commit 89d296ef533525a1378529be66b22d6a2c01e530 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:22 2024 +0000

    picoCTF{t1m3m@ch1n3_186cd7d7}

kali@kali:~/Documents/picoCTF/picoCTF2024/time_machine/drop-in$ 

```
2. La bandera es :
picoCTF{t1m3m@ch1n3_186cd7d7}
## Notas adicionales

## Referencias
