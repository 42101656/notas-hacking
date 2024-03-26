## Objetivo
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 56491`
## Pistas

## Solución
1. Ir a terminal de Linux y hacer lo siguiente:
```
kali@kali:~/Documents/picoCTF/picoCTF2024/binhexa$ nc titan.picoctf.net 56491

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 10000100
Binary Number 2: 10111111


Question 1/6:
Operation 1: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0101000011
Correct!

Question 2/6:
Operation 2: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10000100
Correct!

Question 3/6:
Operation 3: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10111111
Correct!

Question 4/6:
Operation 4: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 0110001001111100
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 100001000
Correct!

Question 6/6:
Operation 6: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 1000010
Incorrect. Try again
Enter the binary result: 1011111 
Correct!

Enter the results of the last operation in hexadecimal: 5F

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}


```
2. La bandera es :
picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6862762d}
## Notas adicionales

## Referencias
https://www.calculator.net/binary-calculator.html
https://gchq.github.io/CyberChef/